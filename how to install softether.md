<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">sudo su - root</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">apt-get update &amp;&amp; apt-get install wget nano build-essential -y</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">wget <strong>https://github.com/SoftEtherVPN/SoftEtherVPN_Stable/releases/download/v4.28-9669-beta/softether-vpnserver-v4.28-9669-beta-2018.09.11-linux-x64-64bit.tar.gz</strong></span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">tar xzvf <strong>softether-vpnserver-v4.28-9669-beta-2018.09.11-linux-x64-64bit.tar.gz</strong></span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">cd vpnserver</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">make</span></li>
</ul>
<table style="height: 26px; width: 110px;">
<tbody>
<tr>
<td style="width: 102px;">select <strong>1</strong>, <strong>1</strong>, <strong>1</strong></td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">cd ..</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">mv vpnserver /usr/local</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;sudo su - root&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">cd /usr/local/vpnserver/</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;chmod 600 *&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">chmod 600 *</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;chmod 600 *&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">chmod 700 vpnserver</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;chmod 600 *&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">chmod 700 vpncmd</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;chmod 600 *&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">nano /etc/init.d/vpnserver</span></li>
</ul>
<table style="height: 296px;" width="462">
<tbody>
<tr>
<td style="width: 452px;">#!/bin/sh<br /># chkconfig: 2345 99 01<br /># description: SoftEther VPN Server<br />DAEMON=/usr/local/vpnserver/vpnserver<br />LOCK=/var/lock/subsys/vpnserver<br />test -x $DAEMON || exit 0<br />case "$1" in<br />start)<br />$DAEMON start<br />touch $LOCK<br />;;<br />stop)<br />$DAEMON stop<br />rm $LOCK<br />;;<br />restart)<br />$DAEMON stop<br />sleep 3<br />$DAEMON start<br />;;<br />*)<br />echo "Usage: $0 {start|stop|restart}"<br />exit 1<br />esac<br />exit 0</td>
</tr>
<tr>
<td style="width: 452px;">press <strong>ctrl+O</strong> to save</td>
</tr>
<tr>
<td style="width: 452px;">press <strong>ctrl+X</strong> to exit</td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">mkdir /var/lock/subsys</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">sudo su</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">chmod 755 /etc/init.d/vpnserver &amp;&amp; /etc/init.d/vpnserver start</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">chkconfig --add vpnserver</span></li>
</ul>
<table style="height: 26px;" width="388">
<tbody>
<tr>
<td style="width: 378px; text-align: center;">if no chkconfig</td>
</tr>
<tr>
<td style="width: 378px;">
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;nano /lib/systemd/system/vpnserver.service&quot;}" data-sheets-userformat="{&quot;2&quot;:515,&quot;3&quot;:{&quot;1&quot;:0},&quot;4&quot;:[null,2,12040119],&quot;12&quot;:0}">nano /lib/systemd/system/vpnserver.service</span></li>
</ul>
</td>
</tr>
<tr>
<td style="width: 378px;">&nbsp;[Unit]<br />Description=SoftEther VPN Server<br />After=network.target<br />[Service]<br />Type=forking<br />ExecStart=/usr/local/vpnserver/vpnserver start<br />ExecStop=/usr/local/vpnserver/vpnserver stop<br />[Install]<br />WantedBy=multi-user.target</td>
</tr>
<tr>
<td style="width: 378px;">press <strong>ctrl+O</strong> to save</td>
</tr>
<tr>
<td style="width: 378px;">press <strong>ctrl+X</strong> to exit</td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">cd /usr/local/vpnserver</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;mkdir /var/lock/subsys&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">./vpncmd</span></li>
</ul>
<table>
<tbody>
<tr>
<td>select <strong>1</strong></td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<table>
<tbody>
<tr>
<td>input VPS IP adress ex: <strong>127.0.0.1</strong></td>
</tr>
<tr>
<td>press <strong>Enter</strong> without inputting anything.</td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;ServerPasswordSet&quot;}" data-sheets-userformat="{&quot;2&quot;:33554432,&quot;28&quot;:1}">ServerPasswordSet</span></li>
</ul>
<table>
<tbody>
<tr>
<td><strong>vpn</strong></td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;HubCreate vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">HubCreate <strong>vpn</strong></span></li>
</ul>
<table>
<tbody>
<tr>
<td><strong>vpn</strong></td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">Hub <strong>vpn</strong></span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">SecureNatEnable</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">UserCreate <strong>vpn</strong></span></li>
</ul>
<table style="height: 28px;" width="157">
<tbody>
<tr>
<td style="width: 147px;">press <strong>Enter </strong>3 times</td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">UserPasswordSet <strong>vpn</strong></span></li>
</ul>
<table>
<tbody>
<tr>
<td><strong>vpn</strong></td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">IPsecEnable</span></li>
</ul>
<table style="height: 43px; width: 192px;">
<tbody>
<tr>
<td style="width: 184px;"><strong>yes, yes, yes, vpn, vpn</strong></td>
</tr>
</tbody>
</table>
<ul>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">VpnOverIcmpDnsEnable /ICMP:yes /DNS:yes</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">exit</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">cd</span></li>
<li><span data-sheets-value="{&quot;1&quot;:2,&quot;2&quot;:&quot;Hub vpn&quot;}" data-sheets-userformat="{&quot;2&quot;:33554945,&quot;3&quot;:{&quot;1&quot;:0},&quot;12&quot;:0,&quot;28&quot;:1}">/etc/init.d/vpnserver restart</span></li>
</ul>
