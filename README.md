# weaponizer
This repository contains a script that provide you the possibility to install automatically a set of hacking tools using docker.

The tools that will be installed are
- [theHarvester](https://github.com/laramies/theHarvester) search email, subdomain and host directly releated to your target
- [nmap](https://nmap.org/) is a most famous security and port scanner tool
- [RustScan](https://github.com/RustScan/RustScan) is a modern (and faster) port scanner
- [sqlmap](http://sqlmap.org/) is an open source penetration testing tool that automates the process of detecting and exploiting SQL injection
- [nikto](https://cirt.net/Nikto2) is a web server scanner
- [metasploit](https://www.metasploit.com/) is the most famous penetration testing tool
- [wpscan](https://wpscan.org/) WordPress security scanner tool

## Requirements
- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Docker](https://docs.docker.com/get-docker/)

## Installing
First of all clone this repository
```sh
git clone https://github.com/lorenzodisidoro/weaponizer.git
````
Run the install script
```sh
./weaponizer install
```

## Usage
### theHarvester
```sh
docker run --rm $(whoami):theharvester -h
```

### Nmap
```sh
docker run --rm $(whoami):nmap -h
```

### RustScan
```sh
docker run -it --rm --name rustscan rustscan/rustscan:v1.9.0 -h
```

### Metasploit
```sh
docker run --rm -it -v "${HOME}/.msf:/home/msf/.msf4" -p 4444:4444 metasploitframework/metasploit-framework ./msfconsole
```

### sqlmap
```sh
docker run --rm $(whoami):sqlmap -h
```

### Nikto
```sh
docker run --rm $(whoami):nikto -h
```

### WPScan
```sh
docker run --rm $(whoami):wpscan -h
```

###
If you want access a file (e.g. password list), you have to mount the password file with -v.
Following an example that show you how to provide the wordlist file to wpscan command in order to perform a brute force attack:
```sh
docker run -it -v "~/local/path/wordlist.txt":/wpscan/wordlist.txt --rm $(whoami):wpscan --url www.hackme.net --usernames admin -P wordlist.txt
```

## Remove docker image
Run the following command to uninstall a tool
```sh
./weaponizer uninstall <TOOL_NAME>
```
