# Notizen Präsentation:

## 01 Übersicht Heal:
### System
- Linux Maschine
- Webanwendung die Resume PDFs generieren soll
- Subdomain Survey Tool gefunden

### Persönliche Highlights:
-  Besonders cool, dass so viele Technologien beteiligt waren:
	- Ruby
    - Python
    - PHP
    - Survey Tool
    - Container Health Checks



## 02 Hürden:
### Datenbankzugriff (LFI):
- Wie Schwachstelle gefunden?
  * Beim Enumeraten die api subdomain gefunden
  * Mit BurpSuite den Traffic überwacht
  * Pfade gefunden

- Was ausgenutzt?
  * Ausgenutzt, dass alle access control allow methods erlaubt waren
  * Ausgenutzt, dass keine Validierung oder Filtering stattgefunden hatte (whitelistet begriffe + ../../)
 
- Welche Folgen?
  * Datenbankzugriff

### Root
- Wie Schwachstelle gefunden?
  * Google

- Was ausgenutzt?
  * Falsche Konfiguration

- Welche Folgen?
  * Dadurch, dass kein ACL Token verwendet -> Neuen Service registrieren möglich
  * Service hatte Health Checks, die in intervallen ausgeführt wurden
  * Health Check wurde ausgeführt, welcher dann eine Reverse Shell gestartet hatte und sich mit uns verbunden hatte



## 03 Gemachte Fehler:
- /etc/hosts
	* test
	* test



## 04 Erkenntnisse:
- Vorgehensweise:
	* Wesentlich verbessert
	* Nicht mehr in allem eine Schwachstelle sehen -> etwas besser einschätzen was überhaupt sein kann und was nicht

- Generelles
	* Risikofaktoren:
		- Was kann alles ausgenutzt werden -> Hilft Software sicherer zu machen
		- Grade sowas wie eine LFI vermeiden
		- Wie wichtig Input Validierung/Filterung ist 
		  (auch in Anwendungssicherheit schon gesehen, aber bei Box nochmal bisschen was anderes, wenn man sieht was daraus entstehen kann)

	* Umgang mit Linux (Commands) + das Windows schlecht ist was Sicherheit angeht xD








