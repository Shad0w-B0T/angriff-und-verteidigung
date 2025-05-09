# Root Access

## Active Ports with User
![linpeas-active-ports.png](../../../img/linpeas-active-ports.png)

### Local Port Forwarding
```
ssh -L 1337:127.0.0.1:8500 ron@heal.htb

ssh -L <LOCAL PORT>:<REMOTE IP>:<REMOTE PORT> <USER>@<SERVER>
```
![img.png](../../../img/ssh-local-port-forwarding.png)

- Only response on port 8500

![img.png](../../../img/consul-webapp-version.png)
---

### Enumerate Consul

1. Check for exploits on exploit db Version ```v1.19.2```
- Found:
  - https://www.exploit-db.com/exploits/51117

2. Try it


---

Keine Ahnung wie ich das hinbekommen habe
![Screenshot 2025-05-09 211701.png](Screenshot%202025-05-09%20211701.png)


```
http://127.0.0.1:1337/ui/server1/services/Ruby%20API%20service/intentions/create
```









