To set up an IP alias, execute the following:

# ifconfig eth0:0 192.168.5.12 netmask 255.255.255.0 up

This assigns the IP address 192.168.5.12 to eth0 as the first alias (noted as eth0:0) on eth0. If you look at the output of ifconfig, you'll see the distinct IP address for eth0 and another for eth0:0.

If you need to add another IP address, just run the same command as root, and increment the alias number. In this example, the next alias number would be eth0:1.

On Mandrakelinux, Red Hat, and similar systems, you can make aliases automatic by creating files in /etc/sysconfig/network-scripts/. In this directory, create a new file called ifcfg-eth0:0 that contains the following contents:

IPADDR="192.168.5.12"
NETMASK="255.255.255.0"

On systems that don't use these network scripts, just add the call to ifconfig directly in your startup script (usually /etc/rc.d/rc.local).
