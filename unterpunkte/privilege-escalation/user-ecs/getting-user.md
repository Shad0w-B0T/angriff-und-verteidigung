# User Access

## Linpeas

### Schreibzugriff finden um linpeas auf den Server zu laden
Script:
https://github.com/peass-ng/PEASS-ng/tree/master/linPEAS

1. ```/tmp``` alle rechte

![img.png](../../../screenshots/temp-dir-all-rights.png)

2. Schreibe/Lese Rechte

![img.png](../../../screenshots/temp-access.png)

3. HTTP Server über Python hochfahren und das linpeas script bereitstellen

![img.png](../../../screenshots/python-http-server.png)

4. linpeas script von Server herunterladen

![img.png](../../../screenshots/linpeas-script-download.png)

5. Execute Rechte hinzufügen
```
chmod +x linpeas.sh
```
![img.png](../../../screenshots/linpeas-add-execute-rights.png)


### Linpeas ausführen und auswerten

#### 1. System Infos
![img.png](../../../screenshots/linpeas-system-infos.png)

#### 2. Linux Exploit Suggestions
![img.png](../../../screenshots/linpeas-exploit-suggestion.png)

#### 3. Cron Jobs
![img.png](../../../screenshots/cron-jobs.png)

#### 4. Active Ports
- Interesting because of the new Ports

![linpeas-active-ports.png](../../../screenshots/linpeas-active-ports.png)

1. Search how to access internal ports from outside
    - ssh local port forwarding
    - Quelle:
        - https://snapshooter.com/learn/linux/how-to-ssh-tunel-proxy
        - https://www.youtube.com/watch?v=F-ubwghsWPM

2. Need ssh password to be able to access internal ports
3. Get User access first

#### 5. Useful software / installed compilers
![img.png](../../../screenshots/linpeas-useful-software.png)

#### 6. PostgreSQL Files
![img.png](../../../screenshots/postgresql-files.png)

#### 6. Found config files with password

![img_1.png](../../../screenshots/linpeas-config-password-found.png)

- Inside the config file:
  ![img.png](../../../screenshots/detailed-config-file.png)



### Newly found password usage

#### 1. Try in db
![img_1.png](../../../screenshots/ask-psql-installed.png)

```
psql -d survey -h localhost -p 5432 -U db_user -W

    -d = DB
    -h = HOST
    -p = PORT
    -U = USER
    -W = Connect via password
```
![img_2.png](../../../screenshots/psql-db-access.png)
- Nothing of value to get user access


#### 2. Try Passwords with other Users
- Ron works

![img.png](../../../screenshots/user-access.png)

![img.png](../../../screenshots/user-flag.png)
#### User flag
![img.png](../../../screenshots/htb-confirmed-user-flag.png)
- Now I can connect to ron via ssh with his credentials
---