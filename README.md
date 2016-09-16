Uma lista com informações úteis para análise forense dividido em tópicos:

[Programas Windows] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#programas-windows)                      
[Programas Linux] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#programasdistros-linux)                   
[Programas Multiplataformas/Web] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#programas-web--linux--windows)                               
[TTL] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#ttl)                                                  
[Hosts] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#hosts)                                              
[Attrib] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#attrib)                                            
[UAC] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#alterar-uacuser-account-control)                      
[Remoção Completa Usuário Linux] (https://gist.github.com/bcamera/b96b0aae1d5b0e51e6de123d0b2167a0#remo%C3%A7%C3%A3o-completa-de-usu%C3%A1rio-linux)

##Programas Windows

Alguns programas para windows que ajudam a análise forense ou ao combate á essa mesma análise.

Programa | Função | Link
------------ | ------------- | -------------
Fciv | Checksum | https://www.microsoft.com/en-us/download/details.aspx?id=11533
usbReadOnly | Autorun/Leitura/Escrita Mídias | https://github.com/bcamera/Meus-Scripts/blob/master/Windows/usbReadOnly.bat
Eraser | Deletar e Sobrescrever dados |http://eraser.heidi.ie/ 
BlueScreenView | Visualizar Dump | http://www.nirsoft.net/utils/blue_screen_view.html#DownloadLinks
  

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
