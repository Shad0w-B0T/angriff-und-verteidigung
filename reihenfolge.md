# Reihenfolge

## Initial Enumeration - DONE

## Exploitation - DONE

### First unprivileged shell
1. [Unprivileged Shell](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#reverse-shell)

2. [Upgrade to Terminal](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#upgrade-dumb-shell-to-fully-functional-terminal-to-be-able-to-enumerate-better)

3. [Shell enumeration](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#continue-enumeration)

4. [Linpeas Script herunterladen + auswerten](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#linpeas)

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
1. [Try newly found pw everywhere](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#newly-found-password-usage)
- switch user root => nope
- switch user ralph => nope
- switch user ron => yep 
  - [User flag](unterpunkte/gaining-access_DONE/system-access/gaining-system-access.md#user-flag)

---

### Getting root access
1. [Remember internal ports from linpeas script](unterpunkte/privilege-escalation/root-esc/getting-root.md#active-ports-with-user)
- Local Port Forwarding via ssh

2. [Found new tool "consul"](unterpunkte/privilege-escalation/root-esc/getting-root.md#enumerate-consul)
- Check for CVE's
- use script -> didnt work because didnt have acl token
- search for acl token
- find config for it / search in docs for it
- see i dont need it bc policy is set to allow anyway
- adjust script
- => BOOM ROOT

3. [Root flag](unterpunkte/privilege-escalation/root-esc/getting-root.md#root-flag)





---

---