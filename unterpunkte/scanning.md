# Reconnaissance (Passive Aufklärung)

# Nmap scan
![nmap-scan.png](../img/nmap-scan.png)

Nmap:
Command zusammengebaut mit der Hilfe von: https://www.stationx.net/nmap-cheat-sheet/

---
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

---
### => Ergebnis:
- Port 22 (ssh) offen
- Port 80 (http) offen 
  - => Es läuft eine Website auf nginx 1.18.0 (Ubuntu)

![img.png](../img/website.png)
---
---
# WhatWeb Scan
![img.png](../img/whatweb-scan.png)

http://heal.htb [200 OK] 
Country[RESERVED][ZZ],
HTML5,
HTTPServer[Ubuntu Linux][nginx/1.18.0 (Ubuntu)],
IP[10.10.11.46],
Script, 
Title[Heal],
X-Powered-By[Express], 
nginx[1.18.0]
---


# Nikto Scan
![img.png](../img/nikto-scan.png)
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


---
# Website Enumeration

Account erstellen:
![img.png](../img/signup.png)

geht nicht:
![img_1.png](../img/signup-with-network.png)

## Subdomains fuzzen
command zusammengebaut von: https://cheatsheet.haax.fr/web-pentest/tools/ffuf/

![ffuf-api-endpoints.png](../img/ffuf-api-endpoints.png)

- keine endpoints gefunden die man aufrufen kann

---

## BurpSuite - Requests anschauen
![img.png](../img/burp-suite.png)

Interessant weil dort Parameter zu sehen sind:
### api.heal.htb

![img.png](api-heal-htb.png)
Ich habe den api.heal.htb Pfad relativ früh bei BurpSuite bemerkt, jedoch habe
ich total vergessen diesen in die /etc/hosts Datei einzutragen und habe mich dann 
viel zu lange mit allem anderen befasst und mich gewundert warum es nicht geht. 
Die genaue Anzahl an Stunden die ich damit verschwendet habe will ich nicht nennen xD

---
### GET   http://heal.htb/sockjs-node/info?t=1745497786739
Aufruf: ![GET_param_1.png](../img/GET_param_1.png)

- Response:
```
  {
    "websocket": true,
    "origins": ["*:*"],
    "cookie_needed": false,
    "entropy": 1009027318
  }
```
Websockets sind erlaubt 
=> Erstmal anschauen wie Websockets funktionieren:
- https://www.youtube.com/watch?v=1BfCnjr_Vjg
- https://www.youtube.com/watch?v=xIjnXwob8ic (Richtig gute und ausführliche Erklärung!)
- https://book.hacktricks.wiki/en/pentesting-web/websocket-attacks.html?highlight=websocke#what-are-websockets (Hier geschaut, wie die initiale WS verbindung aussieht)

=> weitere Requests anschauen um zu sehen, wo die Verbindung aufgebaut werden soll

---
### GET http://heal.htb/sockjs-node/987/dw5uclg4/websocket
Websocket Verbindungsaufbau:
- Initial über HTTP
- Upgrade auf WS

#### Initial über HTTP:
![img_1.png](../img/websocket-request_doesnt-work.png)
- Verbindung soll aufgebaut werden, aber die Websocket Request ist nicht valide 
  - Warum?
    - t

#### Upgrade auf WS
test

---
### POST  http://heal.htb/sockjs-node/862/jmm2xqzl/xhr_streaming?t=1745497787461
Aufruf: ![POST_param_1.png](../img/POST_param_1.png)
- Ergebnis: 405 Error

---

### GET   http://heal.htb/sockjs-node/862/un0nxlzy/htmlfile?c=_jp.aqe2epm
Aufruf: ![GET_param_2.png](../img/GET_param_2.png)

Eine Response wird angezeigt -> Don't panic!

Response:
![img.png](../img/GET-response-param-2.png)
- Script ist hier erkennbar -> daraus kann man schließen, dass es JavaScript ist und kein php, python, etc
```
 <script>
    document.domain = document.domain;
    var c = parent._jp.aqe2epm;
    c.start();
    function p(d) {c.message(d);};
    window.onload = function() {c.stop();};
  </script>
```
```
c.start: 
- Startet die Websocket Verbindung

window.onload: 
- Wenn das window refresht wird -> Websocket Verbindung wird beendet
```



Weiter:
- ausprobieren ob LFI möglich ist und ich so an mehr informationen herankomme
  ![img.png](../img/LFI_try.png)


### XSS
- Nach sockjs cve gegoogelt und herausgefunden, dass es eine DoS und XSS Schwachstelle gibt: 
  - https://security.snyk.io/package/npm/sockjs
    - XSS möglich in allen Versionen die <0.3.0
    - XSS versucht
    - PoC: https://github.com/theyiyibest/Reflected-XSS-on-SockJS
      - hat nicht geklappt => Version muss >=0.3.0 sein
    - CVE XSS: https://cve.mitre.org/cgi-bin/cvename.cgi?name=2020-8823
---

 