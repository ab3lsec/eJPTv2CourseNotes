# Enumerating FTP Port
### CHECKING FOR ANONYMOUS LOGIN:

```
nmap -sC -sV <TARGET>

OR

nmap -p21 --script ftp-anon <TARGET>
```
### BRUTEFORCING FTP LOGIN:

#### METHOD1: HYDRA

```sh
hydra -L /Uname/Worldist -P /Pwd/Wordlist "TARGET" ftp

#If you have a specfic usernmae:
hydra -l root -P /Pwd/Wordlist "TARGET" ftp
```

#### METHOD 2: NMAP NSE SCRIPT

```sh
nmap --script ftp-brute --script-args userdb=/Path/to/Wordlist-p 21 <host>
```

