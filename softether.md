sudo su - root<br/>
apt-get update && apt-get install wget nano build-essential -y<br/>
wget https://github.com/SoftEtherVPN/SoftEtherVPN_Stable/releases/download/v4.28-9669-beta/softether-vpnserver-v4.28-9669-beta-2018.09.11-linux-x64-64bit.tar.gz<br/>
tar xzvf softether-vpnserver-v4.28-9669-beta-2018.09.11-linux-x64-64bit.tar.gz<br/>
cd vpnserver<br/>
make<br/>
<code>select 1,1,1</code>
cd ..<br/>
mv vpnserver /usr/local
cd /usr/local/vpnserver/
chmod 600 *
chmod 700 vpnserver
chmod 700 vpncmd
nano /etc/init.d/vpnserver
<code>#!/bin/sh
# chkconfig: 2345 99 01
# description: SoftEther VPN Server
DAEMON=/usr/local/vpnserver/vpnserver
LOCK=/var/lock/subsys/vpnserver
test -x $DAEMON || exit 0
case "$1" in
start)
$DAEMON start
touch $LOCK
;;
stop)
$DAEMON stop
rm $LOCK
;;
restart)
$DAEMON stop
sleep 3
$DAEMON start
;;
*)
echo "Usage: $0 {start|stop|restart}"
exit 1
esac
exit 0
</code>
mkdir /var/lock/subsys
sudo su
chmod 755 /etc/init.d/vpnserver && /etc/init.d/vpnserver start
chkconfig --add vpnserver
cd /usr/local/vpnserver
./vpncmd
<code>select 1</code><code>enter IP address</code>
