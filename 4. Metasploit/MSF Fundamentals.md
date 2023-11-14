#### HISTORY OF METASPLOIT:
- Metasploit is an open source project and a penetration testing framework with a large collection exploits and scanners.
- It was developed by H. Moore
- First released in 2003

#### MSF MODULES:

- EXPLOIT: they are used to take advantage of a vulnerability usually paired with a payload to ultimately gain access to the target. *Example: Eternal Blue Exploit*

- PAYLOAD: it is a piece of code transferred to the target which executes on the target and exploit a vulnerability. *Example: windows/meterpreter/reverse_tcp*

- ENCODERS: they are used to encode the payload to escape or evade Antivirus detection. *Example: "shikata_ga_nai" in Windows*

- NOPS: they are used to ensure the stability and consistency of the exploit payload which prevents the target from crashing.

- AUXILIARY: They are used for scan for a possible vulnerability as part of Information gathering and enumeration process. *Example: Port Scanner*

#### TYPES OF PAYLOADS:

- NON STAGED PAYLOAD: payload along with exploit is sent all at once
- STAGED PAYLOAD: the process happens stage by stage.

PROCESS OF DELIVERING A STAGED PAYLOAD:
1. The Payload is divide into two parts : Stager and Stage
2. "STAGER" is the first part which is responsible for establishing a connection between the target and the attacker making a way for the payload to get downloaded and executed.
3. "STAGE" is the second part which is responsible for downloading the components of the payload onto the target.

#### MSF MODULES FOR EACH PENTEST PHASES:

1. *Information Gathering* : AUXILIARY MODULES
2. *Enumeration*:  AUXILIARY MODULES
3. *Vulnerability Scanning:*  AUXILIARY MODULES, NESSUS
4. *Exploitation*: EXPLOITS AND PAYLOAD MODULES
5. *Post Exploitation:* METERPRETER
6. *Privilege Escalation:* METERPRETER, POST MODULES
7. *Persistence/Maintaining Access:* METERPRETER, POST MODULES