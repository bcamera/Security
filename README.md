Uma lista com informações úteis para análise forense dividido em tópicos:

[Programas Windows] (https://github.com/bcamera/Security/blob/master/README.md#programas-windows)                      
[Programas Linux] (https://github.com/bcamera/Security/blob/master/README.md#programasdistros-linux)                   
[Programas Multiplataformas/Web] (https://github.com/bcamera/Security/blob/master/README.md#programas-web--linux--windows)      
[Programas Android] (https://github.com/bcamera/Security/blob/master/README.md#programas-android)                               
[TTL] (https://github.com/bcamera/Security/blob/master/README.md#ttl)                                                  
[Hosts] (https://github.com/bcamera/Security/blob/master/README.md#hosts)                                              
[Attrib] (https://github.com/bcamera/Security/blob/master/README.md#attrib-terminal-windows)                                  
[UAC] (https://github.com/bcamera/Security/blob/master/README.md#alterar-uacuser-account-control)                      
[Remoção Completa Usuário Linux] (https://github.com/bcamera/Security/blob/master/README.md#remo%C3%A7%C3%A3o-completa-de-usu%C3%A1rio-linux)                   
[Modificar times de arquivos no Linux] (https://github.com/bcamera/Security#modificar-times-de-arquivos-no-linux-de-forma-an%C3%B4nima)                   
[Curiosidades sobre linha de comando] (https://github.com/jlevy/the-art-of-command-line/blob/master/README-pt.md)               
[Senha Grub] (https://github.com/bcamera/Security/blob/master/README.md#inserir-senha-criptografada-no-grub-debian)

##Programas Windows

Alguns programas para windows que ajudam a análise forense ou ao combate á essa mesma análise.

Programa | Função | Link
------------ | ------------- | -------------
Fciv | Checksum | https://www.microsoft.com/en-us/download/details.aspx?id=11533
usbReadOnly | Autorun/Leitura/Escrita Mídias | https://github.com/bcamera/Meus-Scripts/blob/master/Windows/usbReadOnly.bat
Eraser | Deletar e Sobrescrever dados |http://eraser.heidi.ie/ 
BlueScreenView | Visualizar Dump | http://www.nirsoft.net/utils/blue_screen_view.html#DownloadLinks
WhoCrashed | Visualizar Dump | http://www.resplendence.com/whocrashed
Comodo Program Manager | Monitor de instalação de programas | https://www.comodo.com/home/support-maintenance/programs-manager.php
Glasswire | Monitor de Rede | https://www.glasswire.com/download/
  

##Programas/Distros Linux

Alguns programas e distribuições linux que ajudam a análise forense ou ao combate á essa mesma análise.

Programa/Distro | Função | Link
------------ | ------------- | -------------
Santoku | Perícia Mobile | https://santoku-linux.com/
Caine | Perícia Digital | http://www.caine-live.net/
Deft  | Perícia Digital | http://www.deftlinux.net/
Kali | Perícia Digital/Pentest | https://www.kali.org/
Foremost | Recuperação de dados | http://linux.die.net/man/1/foremost
Shred | Deletar e Sobrescrever dados | http://linux.die.net/man/1/shred
Xplico | Sniffing | http://www.xplico.org
Tcpdump | Sniffing | http://www.tcpdump.org/
TcpSlice | Filtragem | http://linux.die.net/man/8/tcpslice
Hexdump | Editor Hexadecimal | http://linux.die.net/man/1/hexdump
Bless | Editor Hexadecimal (gui) | http://home.gna.org/bless/downloads.html
Dnsmap | Scan de DNS | https://code.google.com/archive/p/dnsmap/downloads
Dnsenum | Scan de DNS | https://code.google.com/archive/p/dnsenum/downloads



##Programas WEB / Linux / Windows

Alguns programas multiplataforma e distribuições linux que ajudam a análise forense.

Programa/Distro | Função | Link
------------ | ------------- | -------------
CapAnalysis | Sniffing | http://pcap.capanalysis.net/
Wireshark | Sniffing  | https://www.wireshark.org/
Autopsy | Recuperação de Dados | http://www.autopsy.com/
Maltego | Banco de dados com mining data | http://www.paterva.com/web7/downloads.php  
Redbot | Extração de informações de um site | https://redbot.org

###Programas Android

Programa | Função | Link
----------- | ----------- | -----------
Iptools | Scan de Rede e portas | https://play.google.com/store/apps/details?id=com.ddm.iptools
Network Scanner | Scan de Rede e portas | https://play.google.com/store/apps/details?id=com.easymobile.lan.scanner
Network Mapper | Nmap | https://play.google.com/store/apps/details?id=org.kost.nmap.android.networkmapper
Opera VPN | VPN | https://play.google.com/store/apps/details?id=com.opera.vpn

###TTL

Campo presente em cabeçalhos de diferentes protocolos que informam o tempo de vida (saltos) que um pacote pode permanecer ativo antes de ser descartado, aqui vemos que baseado no ttl podemos saber com qual sistema estamos lidando e como burlar isso.

Sistema | Valor Padrão
------------ | -------------
Free/Net/OpenBsd | 255
Linux | 255
Roteadores (Cisco) | 255
Switches (3com) | 30
Windows | 128

Ignorar todos os pedidos icmp: echo "1" > /prop/sys/net/ipv4/icmp_echo_ignore_all                                             
Alterar a resposta ttl: echo "128" > /prop/sys/net/ipv4/ip_default_ttl

###Hosts

Um dns local que direciona o endereço para um ip que for cadastrado, podendo ser usado para pharming.

Sistema | Localização
------------ | -------------
Linux | /etc/hosts
Mac OS | /etc/hosts
Windows | %WINDIR%\system32\drivers\etc\hosts

###Attrib (Terminal Windows)

Parâmetro | Função
------------ | -------------
+ | Acrescenta um atributo
- | Retira um atributo
R | Atributo somente leitura
A | Atributo de arquivo morto
S | Atributo de arquivo do sistema
H | Atributo de arquivo oculto
/s |  Inclui todos os arquivos do diretório definido e todos os seus subdiretórios
/d |  Inclui diretórios no processamento (necessita da opção /s)

Exemplo usado para forçar exibir todos os arquivos do diretório:  attrib /s /d -r -s –h


###Alterar UAC(User Account Control)

No Registro: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System no EnableLUA:
UAC Enabled: 1
UAC Disabled: 0

Nas políticas de segurança local: Políticas Locais > Opções de Segurança > Controle de Conta...

###Remoção Completa de Usuário Linux

http://www.cyberciti.biz/faq/linux-remove-user-command/

ps:fazer script depois.

###Modificar times de arquivos no Linux de forma anônima
Fonte (Source) : [ShellHacks] (http://www.shellhacks.com/en/Categories/Penetration)
Files in Linux have 3 types of timestamps: Access (atime), Modify (mtime) and Change (ctime).

Access (atime) and modification (mtime) timestamps can be easily changed using touch command, but there is no a standard way to set a different change (ctime) timestamp.

As a possible workaround you can set the system time to the ctime you want to impose, then touch the file and then restore the system time.

Use the stat command to see the current file's timestamps :

$ stat file.txt
  File: ‘file.txt’
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file
Device: 804h/2052d	Inode: 2501536     Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/     admin)   Gid: ( 1000/     admin)

Access: 2015-02-19 11:43:08.503408793 +0200
Modify: 2015-02-19 11:43:08.503408793 +0200
Change: 2015-02-19 11:43:08.503408793 +0200

Difference Between "Access", "Modify" and "Change" Timestamps
Timestamp 	When it gets updated?
atime 	Access time gets updated when you open a file or when a file is used for other operations like grep, cat, head and so on.
mtime 	Modify time gets updated when you whenever update content of a file or save a file.
ctime 	Change time gets updated when the file attributes are changed, like changing the owner, changing the permission or moving it to another filesystem, but will also be updated when you modify a file.
Changing a File's "Access" and "Modification" Time

Change a file's access time (atime) :

$ touch -a --date="1988-02-15" file.txt
$ touch -a --date="1988-02-15 01:00" file.txt
$ touch -a --date="1988-02-15 01:00:17.547775198 +0300" file.txt

Change a file's modification time (mtime) :

$ touch -m --date="2020-01-20" file.txt
$ touch -m --date="2020-01-20 23:05" file.txt
$ touch -m --date="2020-01-20 23:05:43.443117094 +0400" file.txt

Changing a File's "Change" Time

As i have already said there is no a standard solution to fake a change (ctime) timestam.

Nevertheless. it is possible to set the system time to the ctime you want to impose, then touch the file and then rollback the system time.

Modification of a system time may cause an unexpected impact. Use the below commands on your own risk.

Save the current system's date and time in the variable NOW :

$ NOW=$(date)

Set the fake date and time (requires root) :

$ date --set "2030-08-15 21:30:11"

Touch the file to fake the all timestamps :

$ touch file.txt

Rollback the date and time (requires root) :

$ date --set "$NOW"

To speedup modification and reduce the possible impact, execute the above commands as follows :

$ NOW=$(date) && date -s "2030-08-15 21:30:11" && touch file.txt && date -s "$NOW"

Stay Stealthy ;)

To stay stealthy don't forget to unset the variable, clear logs and history.

Unset the variable NOW :

$ unset NOW

Remove the information about changed time from /var/log/messages (requires root) :

Feb 24 06:32:46 centos7 systemd: Time has been changed
Aug 15 14:30:11 centos7 systemd: Time has been changed

Clear the last login history (requires root) :

$ echo > /var/log/wtmp
$ echo > /var/log/btmp
$ echo > /var/log/lastlog

Read more : How To Clear or Remove Last Login History in Linux

Clear the history of the current session :

$ history -r



###Inserir senha criptografada no grub (Debian)
Como root executar os seguinte comandos:                                                                                        
$ grub-mkpasswd-pbkdf2                                                                                                          
$ vim /etc/grub.d/00_header                                                                                                     
Ao final do arquivo:                                                                                                            
São 4 linhas:                                                                                                                   

cat << EOF
set superusers="usuario"
password_pbkdf2 usuario grub.pbkdf2.sha512.10000.706A070CD168B759801D2790C6 D48D5C3842B9165CF08600918CD9A496B6BFF9CD9BB8F7C99DEC431DF3AD0D466709ECE041F C00C5C1B58F00A879E0322959B7.6FC5058001DFFC1CD6B35F9A5DA66ED6C8745E4999E064E 712C9BF302E8F2547CD0B591C33A340F229FD79D2252E23CFC41410C9A3300537E54C9CE6F7008100
EOF

$ update-grub
