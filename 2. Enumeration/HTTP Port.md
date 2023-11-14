# Enumerating HTTP Port
#### BASIC ENUMERATION:
- `Whatweb` - enumerates valuable info like components used and their versions
- `Wappalyzer` - Alternative of whatweb
- `robots.txt` file - It is a file which all files and directories should be loaded or spider and which all should be denied

```
use auxiliary/scanner/http/robots_txt
```
#### FINDING SUPPORTED HTTP METHODS:

```
nmap <TARGET> --script http-methods --script-args http-methods.url-path='/WEBSITE PATH' 
```

#### VERSION DETECTION USING METASPLOIT:

```
msfconsole
use auxiliary/scanner/http/http_version
set RHOST <TARGET>
exploit
```

#### ENUMERATING WITH CURL

```
curl -v <TARGET URL> | more
```

#### DIRECTORY BRUTEFORCING:

```
ffuf -w <DIRECTORY WORDLIST>:FUZZ -u http://<TARGET IP>/FUZZ
```

```
dirb <TARGET WEBSITE>
```
