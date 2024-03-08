1) Ansible Repo hier: https://github.com/lekrieger/ansible

2) Dockerfile aus diesem Repo wird vorerst nicht mehr genutzt, da das Ansible playbook angepasst wurde und kein Apache Container mehr eingesetzt wird 

3)IP Adresse wird im playbook normalerweise automatisch erkannt und in der index.html in /var/www/html ersetzt, aber falls nicht, muss die IP Adresse angepasst werden.
    Alternativ statische IP Konfiguration auf dem Server:
    
    Pfad: cd /etc/network/
    shell: sudo nano interfaces
    
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
