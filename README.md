IP Adressen muessen jedes mal in folgenden Dateien angepasst werden:

1) in der inventory.yml file
2) in der index.html file


Alternativ statische IP Konfiguration:

cd /etc/network/
sudo nano interfaces
Code:
----------------------------------------------
# The loopback network interface
auto lo
iface lo inet loopback


#allow-hotplug enp0s3
#iface enp0s3 inet dhcp

#The primary network interface
auto enp0s3 #Adapter auswaehlen
iface enp0s3 inet static
 address 172.16.2.108 #statische IP
 netmask 255.255.240.0 #statische SN
-----------------------------------------------