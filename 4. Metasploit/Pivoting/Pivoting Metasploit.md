# Pivoting via Metasploit

Pivoting is a Post exploitation technique which utilises a compromised host to attack other systems on the private Internal network.<br>
Imagine you have compromised a host in `192.168.10.0/24` subnet and that host is also part of another subnet `10.10.10.1/24`. This really introduces more systems opening large attack surface.

![pivoting](https://github.com/ab3lsec/eJPTv2CourseNotes/assets/87868050/e217f6d9-fc2d-4b7a-ab10-f9eb47370ca3)


#### HOW TO PIVOT TO OTHER SUBNETS:

1. Gain an initial Meterpreter shell
2. Now we can enumerate the IP configuration on that target to check whether it is part of another subnet
3. Now we need to add the route of VICTIM 2. This will add a route in our local machine to the VICTIM 2 via VICTIM 1.

```
run autoroute -s "VICTIM 2 SUBNET"
```

4. We can then perform a Port Scan of the VICTIM 2

```
use auxiliary/scanner/portscan/tcp 
set RHOSTS 10.5.27.67
exploit
```

5. Since we cannot access VICTIM 2 directly we cannot do a detailed `nmap` scan for version detection etc.. 
6. So we need to perform the Port forwarding, which means communications to Port 80 of VICTIM 2 will be forwarded to a local specified port of our choice

```
portfwd add -l 1234 -p 80 "VICTIM 2 IP"
```

7. Now we can do a NMAP scan. VICTIM 2 port 80 is forwarded to the local port in our local machine. So we need to give `localhost`

```
db_nmap -sV -p1234 localhost
```

