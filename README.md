# se2-cheat-sheet

Die folgenden Befehle gehören zur Kategorie "MySQL-Verbindung" und ermöglichen das Verbinden zu einer MySQL-Datenbank:

    sudo mysql –u root –p: 
    Dieser Befehl verbindet sich mit dem MySQL-Server als Benutzer "root" und fordert das Passwort an.

Die folgenden Befehle gehören zur Kategorie "Benutzerverwaltung" und ermöglichen das Erstellen, Anzeigen und Löschen von Benutzern in der MySQL-Datenbank:

    CREATE USER 'username' IDENTIFIED BY 'password';: Dieser Befehl erstellt einen neuen Benutzer mit dem Namen "username" und dem Passwort "password".
    CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';: Dieser Befehl erstellt einen neuen Benutzer mit dem Namen "username" und dem Passwort "password", der sich nur von dem lokalen Computer aus verbinden kann.
    CREATE USER 'username'@'ip_address' IDENTIFIED BY 'password';: Dieser Befehl erstellt einen neuen Benutzer mit dem Namen "username" und dem Passwort "password", der sich nur von einer bestimmten IP-Adresse aus verbinden kann.
    CREATE USER 'username'@'%' IDENTIFIED BY 'password';: Dieser Befehl erstellt einen neuen Benutzer mit dem Namen "username" und dem Passwort "password", der sich von jeder IP-Adresse aus verbinden kann.
    SHOW GRANTS FOR username;: Dieser Befehl zeigt die Berechtigungen für den Benutzer "username" an.
    DROP USER 'username'@'localhost';: Dieser Befehl löscht den Benutzer "username" und verhindert, dass sich dieser Benutzer von der IP-Adresse "localhost" aus verbinden kann.

Die folgenden Befehle gehören zur Kategorie "Berechtigungsverwaltung" und ermöglichen das Erteilen und Entziehen von Berechtigungen für Benutzer in der MySQL-Datenbank:

    GRANT permission_type ON database.table TO 'username'@'localhost';: Dieser Befehl erteilt dem Benutzer "username" Berechtigungen für die angegebene Datenbank und die angegebene Tabelle.
    GRANT INSERT ON *.* TO 'username'@'localhost';: Dieser Befehl erteilt dem Benutzer "username" Berechtigungen für das Einfügen von Daten in alle Datenbanken und Tabellen.
    GRANT INSERT *database_name.table_name* TO 'username'@'localhost';: Dieser Befehl erteilt dem Benutzer "username" Berechtigungen für das Einfügen von Daten in die angegebene Datenbank und die angegebene Tabelle.
    GRANT ALL PRIVILEGES ON *.* TO 'database_user'@'localhost';: Dieser Befehl erteilt dem Benutzer "database_user" alle Berechtigungen für alle Datenbanken und Tabellen auf dem lokalen Computer.
    GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';: Dieser Befehl erteilt dem Benutzer "database_user" alle Berechtigungen für alle Tabellen in der Datenbank "database_name" auf dem lokalen Computer.
    GRANT ALL PRIVILEGES ON database_name.table_name TO 'database_user'@'localhost';: Dieser Befehl erteilt dem Benutzer "database_user" alle Berechtigungen für die Tabelle "table_name" in der Datenbank "database_name" auf dem lokalen Computer.
    REVOKE permission_type ON database.table TO 'username'@'localhost';: Dieser Befehl entzieht dem Benutzer "username" Berechtigungen für die angegebene Datenbank und die angegebene Tabelle.

Die folgenden Befehle gehören zur Kategorie "Datenbank-Abfragen" und ermöglichen das Abfragen von Daten in der MySQL-Datenbank:

    SELECT User, Host, Password FROM mysql.user;: Dieser Befehl zeigt die Benutzer, die Host-IP-Adressen und die Passwörter für alle Benutzer in der MySQL-Datenbank an.
    SELECT * FROM mysql.user;: Dieser Befehl zeigt alle Spalten für alle Benutzer in der MySQL-Datenbank an.
    select * from RESERVATION;: Dieser Befehl zeigt alle Daten für die Tabelle "RESERVATION" an.
    select * from VEHICLE;: Dieser Befehl zeigt alle Daten für die Tabelle "VEHICLE" an.
    select * from CUSTOMER;: Dieser Befehl zeigt alle Daten für die Tabelle "CUSTOMER" an.
    describe RESERVATION;: Dieser Befehl zeigt die Struktur (Spaltennamen, Datentypen usw.) für die Tabelle "RESERVATION" an.
    describe CUSTOMER;: Dieser Befehl zeigt die Struktur (Spaltennamen, Datentypen usw.) für die Tabelle "CUSTOMER" an.
    describe VEHICLE;: Dieser Befehl zeigt die Struktur (Spaltennamen, Datentypen usw.) für die Tabelle "VEHICLE" an.
    show tables;: Dieser Befehl zeigt alle Tabellen in der aktuellen Datenbank an.

Die folgenden Befehle gehören zur Kategorie "Benutzerverwaltung" und ermöglichen das Ändern von Benutzer-Einstellungen in der MySQL-Datenbank:

    ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';: Dieser Befehl ändert das Passwort für den Benutzer "root" auf dem lokalen Computer.
    flush privileges;: Dieser Befehl aktualisiert die Berechtigungstabelle in der MySQL-Datenbank. Dies ist notwendig, wenn Änderungen an Benutzer-Einstellungen vorgenommen wurden.
    UPDATE mysql.user SET host='%' WHERE user='root';: Dieser Befehl ändert den Host für den Benutzer "root" in der MySQL-Datenbank.
    grant all on freerider_db.* to 'freeriderVSCODE'@'%';: Dieser Befehl erteilt dem Benutzer "freeriderVSCODE" alle Berechtigungen für alle Tabellen in der Datenbank "freerider_db".

Die folgenden Befehle gehören zur Kategorie "Datei-Import" und ermöglichen das Importieren von Dateien in die MySQL-Datenbank:

    cat /mnt/init_freerider_data.sql | mysql --user=freerider --password=free.ride: Dieser Befehl importiert die Datei "init_freerider_data.sql" in die MySQL-Datenbank als Benutzer "freerider" mit dem Passwort "free.ride".
    cat /mnt/init_freerider_schema.sql | mysql --user=root --password=: Dieser Befehl importiert die Datei "init_freerider_schema.sql" in die MySQL-Datenbank als Benutzer "root" ohne Passwort.
