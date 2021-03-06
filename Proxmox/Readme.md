Import OVA
==========
````
tar -xvf Debian9-motioneye.ova
qemu-img convert -f vmdk Debian9-motioneye-disk001.vmdk  -O raw Debian9-motioneye-disk001.raw
# then create a KVM machine
dd if=Debian9-motioneye-disk001.raw of=/dev/pve/vm-1000-disk-1 bs=1M
````

Network copy
============
````
# on pve server
export VMDISK_ID=100
netcat -w30 -vvnlp 3333 | gzip -dc > /dev/pve/vm-$VMDISK_ID-disk-1; date
````

````
# on client 
export FOUT=/media/TOSHIBA_3TB/VirtualBoxVMs/Windows10.raw
export PVE_SERVER=192.168.3.250
vboxmanage clonehd Windows10.vdi $FOUT --format RAW
dd if=$FOUT | gzip -c | nc -w 30 -vvn $PVE_SERVER 3333
````

Show ip on VM banner
====================
````
# add to /etc/issue
IP address: \4
````
