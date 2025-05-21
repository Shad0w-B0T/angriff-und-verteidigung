# Reihenfolge

## Initial Enumeration

### Main Domain Enumeration
1. Webseite enumeration [Main Domain: heal.htb](./unterpunkte/scanning/main-scanning.md#healhtb-domain)
- [Nmap](./unterpunkte/scanning/domains/heal.htb.md#nmap-scan)
- [Whatweb](./unterpunkte/scanning/domains/heal.htb.md#whatweb-scan)
- [Nikto](./unterpunkte/scanning/domains/heal.htb.md#nikto-scan)
- [dirb](./unterpunkte/scanning/domains/heal.htb.md#dirb-scan)
- [Mit BurpSuite alles überwacht](./unterpunkte/scanning/domains/heal.htb.md#burpsuite---requests-anschauen)
  - Erstmal ausprobiert ob bei Pfaden mit Parametern eine LFI möglich ist
  - Dadurch auch bei Websockets geschaut ob das evtl was ist wegen sockjs

2. Login Page angeschaut + User erstellt [Login Page](./unterpunkte/scanning/domains/heal.htb.md#login-page)
- Wieder Burp angeschaut und beim einloggen einen Token bekommen => merken
- Auch gesehen, dass eine subdomain aufgerufen wurde => api.heal.htb => merken

3. Resume Builder -> PDF Generator Seite
- [Resume Builder Page](./unterpunkte/scanning/domains/heal.htb.md#resume-builder-page)
- Buttons ausprobiert
  - Profile
  - Survey [Subdomain gefunden](./unterpunkte/scanning/domains/take-survey.heal.htb.md)
  - PDF generiert und mit Burp geschaut was passiert

> Ergebnis:  
api.heal.hbt  
take-survey.heal.htb  
subdomain gefunden

> In die ```/etc/hosts``` eingetragen


Als erstes angefangen mit der API Domain!

---

### API Domain Enumeration
api.heal.htb gefunden durch BurpSuite

1. API enumeration ```Subdomain: api.heal.htb```
- [Webseite selber aufgerufen](./unterpunkte/scanning/domains/api.heal.htb.md#website-enumeration)
- [Whatweb](./unterpunkte/scanning/domains/api.heal.htb.md#whatweb-scan-httpapihealhtb)
- [Nikto](./unterpunkte/scanning/domains/api.heal.htb.md#nikto-scan-httpapihealhtb)
- [dirb](./unterpunkte/scanning/domains/api.heal.htb.md#dirb-scan-httpapihealhtb)
- [BurpSuite Requests angeschaut](./unterpunkte/scanning/domains/api.heal.htb.md#burpsuite)
  1. Zwei Pfade gefunden wobei bei einem LFI ging
  2. /etc/passwd dadurch bekommen
  3. geschaut welche [weiteren Pfade über LFI auslesbar sind](./unterpunkte/scanning/domains/api.heal.htb.md#weitere-lfi-auf-apihealhtb)
  4. mit ffuf eigene liste laufen lassen (siehe Quellen)
  5. anhand von ffuf [/config/database.yml](./unterpunkte/scanning/api/api-findings.md#configdatabaseyml---dadurch-die-db-gefunden-storagedevelopmentsqlite3) gefunden 

> Ergebnis:  
/config/database.yml gefunden

Damit ich nichts übersehe bei der zweiten Subdomain weitergemacht!

---

### Survey Domain Enumeration
take-survey.heal.htb gefunden durch Button

1. Survey Enumeration ```Subdomain: take-survey.heal.htb```
- [Webseite selber aufgerufen](./unterpunkte/scanning/domains/take-survey.heal.htb.md#subdomain-httptake-surveyhealhtb)
  - Survey gefunden
  - Manuell ausprobieren
  - Herausgefunden, dass Ralph ein Admin für die Survey ist
- [Whatweb](./unterpunkte/scanning/domains/take-survey.heal.htb.md#whatweb-scan-httptake-surveyhealhtb)
  - User Email rausgefunden
- [Nikto](./unterpunkte/scanning/domains/take-survey.heal.htb.md#nikto-scan-httptake-surveyhealhtb)
- [dirb](./unterpunkte/scanning/domains/take-survey.heal.htb.md#dirb-scan-survey)
  - Herausgefunden, dass es einen /admin pfad gibt

> Ergebnis:  
Admin Panel für die Survey  
Ralph ist Admin für LimeSurvey
---

---

## Exploitation

### DB Exploitation (anhand von LFI)
Mit den Infos von der Api Enumeration => /config/database.yml weitermachen

1. [Über die LFI von der API in die config der DB geschaut](./unterpunkte/gaining-access/db-access/gaining-db-access.md#db-access)
- Herausgefunden, dass es ```/storage/development.sqlite3``` Datei gibt
- DB herunterladen per ``curl``
- DB anschauen

2. [Hashed Passwords](./unterpunkte/gaining-access/db-access/gaining-db-access.md#hash-rausfinden)
- Mit diversen Tools herausfinden, was für ein Hash für die PW verwendet wurde
  - hash-identifier => nicht geklappt
  - hashid => hat geklappt
- [Hashcat](./unterpunkte/gaining-access/db-access/gaining-db-access.md#3-hashcat)
  - um PW herauszufinden

> Ergebnis:  
User: Ralph  
PW: 147258369

---

### Admin Panel Exploitation
Mit dem Passwort von der DB Exploitation

1. [Passwort überall ausprobieren](./unterpunkte/gaining-access/system-access/gaining-system-access.md#try-credentials)
- mit ssh versuchen ob ich mich schon auf den server einloggen kann
  - geht nicht
- Admin Panel
  - [geht](./unterpunkte/gaining-access/system-access/gaining-system-access.md#hat-geklappt)



----- !!! DAS HIER MACHT SINN UND ICH SOLL ES REINNEHMEN !!! -----

Admin Panel (LimeSurvey) Enumeration
1. [LimeSurvey Enumeration](./unterpunkte/gaining-access/system-access/gaining-system-access.md#admin-panel-enumeration)
- herausgefunden, dass ich code in die offene survey eintragen kann, der dann von jedem ausgeführt wird
der an der umfrage teilnimmt
  
siehe [Gefahren durch LFI](./unterpunkte/gaining-access/system-access/gaining-system-access.md#gefahren-durch-den-zugriff-auf-das-admin-panel)

> Ergebnis:  
Durch eine einfache LFI bin ich in der Lage den Survey zu bearbeiten und allen
Teilnehmenden ein Script ins Gesicht zu drücken.




2. [Nach CVE suchen](./unterpunkte/gaining-access/system-access/gaining-system-access.md#nach-limesurvey-cves-gesucht)
- etwas gefunden für rev shell => Code herunterladen, anpassen ausführen und ab ins System

> Ergebnis:  
Reverse shell

---

### First unprivileged shell
1. [Unprivileged Shell](./unterpunkte/gaining-access/system-access/gaining-system-access.md#reverse-shell)

2. [Upgrade to Terminal](./unterpunkte/gaining-access/system-access/gaining-system-access.md#upgrade-dumb-shell-to-fully-functional-terminal-to-be-able-to-enumerate-better)

3. [Shell enumeration](./unterpunkte/gaining-access/system-access/gaining-system-access.md#continue-enumeration)

4. [Linpeas Script herunterladen + auswerten](./unterpunkte/gaining-access/system-access/gaining-system-access.md#linpeas)

> Ergebnis:  
> 1. Terminal mit kaum rechten  
> 2. Linpeas script auf Server geladen  
> => System Infos  
> => Cron Jobs  
> => Active Ports  
> => Config files with Password
> 3. /config.php => AdmiDi0_pA$$w0rd
---

---

## Privilege Escalation 

### Getting user access
1. [Try newly found pw everywhere](./unterpunkte/gaining-access/system-access/gaining-system-access.md#newly-found-password-usage)
- switch user root => nope
- switch user ralph => nope
- switch user ron => yep 
  - [User flag](./unterpunkte/gaining-access/system-access/gaining-system-access.md#user-flag)

---

### Getting root access
1. [Remember internal ports from linpeas script](./unterpunkte/priviledge-escalation/root-esc/getting-root.md#active-ports-with-user)
- Local Port Forwarding via ssh

2. [Found new tool "consul"](./unterpunkte/priviledge-escalation/root-esc/getting-root.md#enumerate-consul)
- Check for CVE's
- use script -> didnt work because didnt have acl token
- search for acl token
- find config for it / search in docs for it
- see i dont need it bc policy is set to allow anyway
- adjust script
- => BOOM ROOT

3. [Root flag](./unterpunkte/priviledge-escalation/root-esc/getting-root.md#root-flag)





---

---