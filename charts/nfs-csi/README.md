systemctl enable nfs-server
mkdir -p /mnt/pv
chmod 707 /mnt/pv
chown -R 65534:65534 /mnt/pv 
systemctl start nfs-server
vi /etc/exports
/mnt/pv 192.168.122.0/24(rw,sync,no_root_squash)
/mnt/pv 192.168.222.0/24(rw,sync,no_root_squash)
systemctl restart nfs-server
exportfs -v

