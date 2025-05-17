# Reihenfolge

## Basic Enumeration

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
Ralph ist Admin für LimeSurvey
---


## DB Access
Mit den Infos von der Api Enumeration => /config/database.yml weitermachen

1. [Über die LFI von der API in die config der DB geschaut](./unterpunkte/gaining-access/db-access/gaining-db-access.md#db-access)
- Herausgefunden, dass es ```/storage/development.sqlite3``` Datei gibt
- Herunterladen per ``curl``
- DB anschauen













