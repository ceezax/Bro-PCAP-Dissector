# Bro-PCAP-Dissector
Bro script to dissect PCAP files in a way that facilitates active threat hunting by employing stack counting techniques. The script accepts PCAP fileas an input, scans the existence of major network protocols (i.e. HTTP,DNS,SMB,RDP,SSH,SSL,FTP and IRC) and produce sorted and counted lists of interesting fields/headers upon the existence of any of the previous protocols.

Running the script using this command "bro -C -r trace.pcap pcap-dissector.bro" produces the following samples output


==========================================================
Bytes Downloaded > {1000000 Bytes / 1 MB}
==========================================================
 
    5243355          x.x.x.x   <-------  x.x.x.x  : 80/tcp
    2867458          x.x.x.x   <-------  x.x.x.x  : 443/tcp
    1136345          x.x.x.x   <-------  x.x.x.x  : 443/tcp
    1070806          x.x.x.x   <-------  x.x.x.x  : 443/tcp
   	1029117          x.x.x.x   <-------  x.x.x.x  : 80/tcp
 
==========================================================
Bytes Uploaded > {1000000 Bytes / 1 MB}
==========================================================
 
		2231614               x.x.x.x      -------> x.x.x.x  : 1521/tcp
		2018871               x.x.x.x      -------> x.x.x.x  : 524/tcp
		1734451               x.x.x.x      -------> x.x.x.x  : 22/tcp
		1705043               x.x.x.x      -------> x.x.x.x  : 22/tcp
		1306928               x.x.x.x      -------> x.x.x.x  : 993/tcp
		1299905               x.x.x.x      -------> x.x.x.x  : 25/tcp


==========================================================
Conn Duration > {300 Second / 5 Minutes}
==========================================================
 
	631                   x.x.x.x   <------->     x.x.x.x   : 443/tcp
	506                   x.x.x.x   <------->     x.x.x.x   : 443/tcp
	492                   x.x.x.x   <------->     x.x.x.x   : 443/tcp
	333                   x.x.x.x   <------->     x.x.x.x   : 443/tcp
	329                   x.x.x.x   <------->     x.x.x.x   : 80/tcp  
 
 
==========================================================
Conn Listening_TCP_Ports_on_Private_IPs
==========================================================
 
	1             80/tcp    listening on  x.x.x.x         http
 
 
 
==========================================================
Conn Listening_TCP_Ports_on_Public_IPs
==========================================================
 
	2             443/tcp   -------> -
	5             443/tcp   -------> ssl
	11            80/tcp    -------> http
 

==========================================================
HTTP Odd_Hosts
==========================================================

	1             whos.amung.us
	1             widgets.amung.us
	1             a.topgunn.photography
	1             magusserver.top
	1             ckea.ca
	2             g00.co
	2             x.ss2.us
	2             www.postagens.net
	3             mohecy.tk
	4             185.82.202.170
	6             ululataque-forstbea.bondcroftatvs.co.uk
	7             e7qx9y.he6gnm.top
	15            www.emidioleite.com.br
	23            5.34.183.40


==========================================================
HTTP Odd_URIs
==========================================================

	1             an =    Iniciar{133}  Downlaod                                         x.x.x.x       ------->  www.devyatinskiy.ru
	1             )|utmcmd=organic|                                                      x.x.x.x       ------->  www.google-analytics.com
	1             an =    Iniciar{69}                                                    x.x.x.x       ------->  www.devyatinskiy.ru
	1             ta Pasta === C:\Users\Matthew.F                                        x.x.x.x       ------->  www.devyatinskiy.ru
	1             =    Continuou ... extrair                                             x.x.x.x       ------->  www.devyatinskiy.ru
	1             ks /create /tn "SYSFROGGYPC37"                                         x.x.x.x       ------->  api.devyatinskiy.ru
	1             in A. Abbott | Lit2Go ETC&utm                                          x.x.x.x       ------->  www.google-analytics.com
	1             " /F                                                                   x.x.x.x       ------->  api.devyatinskiy.ru
	1             =render_toolbox|5196&cmenu=null                                        x.x.x.x       ------->  m.addthis.com   
	1             jpd2buu.3sx.vbs" /sc onlogon /R                                        x.x.x.x       ------->  api.devyatinskiy.ru
	1             n =     Iniciar{121} - Download                                        x.x.x.x       ------->  www.devyatinskiy.ru
	1             an =    Iniciar{90}                                                    x.x.x.x       ------->  www.devyatinskiy.ru
	1             40/bibi/dll.dll|P5PKLOY+IYtRWfZ                                        x.x.x.x       ------->  www.devyatinskiy.ru
	1             n|4530|817,sh|4534|5,sh|4537|                                          x.x.x.x       ------->  m.addthis.com   
	1             0,700,400italic|Josefin+Slab:40                                        x.x.x.x       ------->  fonts.googleapis.com
	1             t[1329]                                                                x.x.x.x       ------->  api.devyatinskiy.ru
	1             index.php?N=a37[7]FROGGY-PC-Mat                                        x.x.x.x       ------->  api.devyatinskiy.ru
	1             /tr "C:\Windows\SysWOW64\Java\m                                        x.x.x.x       ------->  api.devyatinskiy.ru
	1             240/bibi/W7.zip|38|http://65.18                                        x.x.x.x       ------->  www.devyatinskiy.ru
	1                Pasta === C:\Users\Matthew.F                                        x.x.x.x       ------->  www.devyatinskiy.ru
	2             [?] Operating syst                                                     x.x.x.x       ------->  www.devyatinskiy.ru
	2               |  _|\x0d                                                            x.x.x.x       ------->  www.devyatinskiy.ru
	2             \Ionic.Zip.Reduc                                                       x.x.x.x       ------->  www.devyatinskiy.ru
	2               |_  |\x0d                                                            x.x.x.x       ------->  www.devyatinskiy.ru
	2             [!] No valid threa                                                     x.x.x.x       ------->  www.devyatinskiy.ru
	2             hLogonW handles..\x0d                                                  x.x.x.x       ------->  www.devyatinskiy.ru
	2             \x09|     |_  |_| |_| . |___| | |_                                     x.x.x.x       ------->  www.devyatinskiy.ru
	2             \x09|  V  |  _|_  | |  _|___|   |_                                     x.x.x.x       ------->  www.devyatinskiy.ru
	2             rogman\AppData\Local\Temp\Java                                         x.x.x.x       ------->  www.devyatinskiy.ru

==========================================================
HTTP Referrers
==========================================================

	1             www.google.com.au
	2             uacltr.securetopc.top
	15            3wzn5p2yiumh7akj.waytopaytosystem.com
	27            -
	51            www.outdoorsamoa.com
	54            au.search.yahoo.com
	56            www.koeppl.com
	86            planetside.co.uk

 
==========================================================
HTTP User-Agents
==========================================================
 
	1             -
	1             Microsoft NCSI
	2             Microsoft-CryptoAPI/6.1
	243           Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko


==========================================================
HTTP Methods
==========================================================
 
	9             POST
	274           GET

==========================================================
HTTP Response_Codes
==========================================================

	1             307
	2             403
	6             404
	6             204
	6             301
	44            302
	232           200
 
==========================================================
HTTP Client_Requests
==========================================================
 
	63            x.x.x.x
	136           x.x.x.x
	198           x.x.x.x


 
  
