# infra

ssh-keygen
ssh-copy-id root@localhost

exit
find <dir> down
-perm /1000
-not -user bob

openssl dgst -sha256 -verify  -signature //

losetup -f /efajh2332
lsblk -f
cryptsetup luksOpen /dev/loop0 loop0

mount /dev/mapper/loop0 /mnt
cp /mnt/* /root

setfacl -m+ -b all -x -
setfacl -m u:operator:rw mess.txt
setfacl -b mess.txt

chown u:g .txt

dd if= of= bs= count=

getfacl

cryptsetup luksFormat /dev/sdc
cryptsetup luksOpen /dev/sdc x
mk.xfs /dev/mapper/x
umount /mnt/
mount /dev/mapper/x /mnt
fdisk /dev/sdc

lusetup -f --show /af90u09ua
cryptsetup luksOpen /dev/loop0 loop
mount /dev/mapper/loop0 /mnt
ls /mnt
cp /mnt/?? /root

openssl aes-128-cbc -d -K -iv -in -ouy

openssl dgst -sha256 -sign private  -out   file
openssl dgst -sha256 -verify  -signature   file

openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:2014 -out 
rsa -noout -text -in
setfacl -m u:operator:r file

fdisk /dev/sdc
n p w
mk.ext2 /dev/sdc1
mount -o ro /dev/sdc1 /mnt


find /target/directory -type f ! -user root -delete
find /... -type f ! -user root -exec rm -f {} \
find /filename -type f ! -user root -print0 | xargs -0 rm -f

chage operator -l 2025-192  -M 100
setuid (4000)  s (if execute bit on) or S (if execute off) in the owner execute slot
setgid (2000) runs with group’s privileges (on files); on directories, new files inherit the directory’s group. Displayed as s/S in the group execute slot.
sticky (1000) – on directories, only file owner can delete; on files, historical (now often ignored). Displayed as t/T in the others execute slot.

del acl: setfacl -b /file

4 o
2 g
1 T

ssh-keygen -y -f k > .ssh/authorized_keys
chmod 444 authro...


openssl genrsa -out factory.key 2048
openssl req -new -key factory.key  -out self.my-factory.eu.req
openssl x509 -req -days 100 -in self.my-factory.eu.req -out self.my-factory.eu.crt -signkey 




Permission rules (key to avoid “Permission denied”)
~/.ssh must be 700 (drwx------)
~/.ssh/authorized_keys must be 600 (-rw-------)
The user’s private key (id_rsa) must be 600

**disk partition** create new partition
fdisk /dev/sdc
 n - p - 1 - w 
 mkfs.ext4 /dev/sdc1
mount - ro /dev/sdc1 /mnt
mount | grep /mnt

**enc file**
cryptsetup luksFormat /----
luksDump
luksClose

cryptsetup luksOpen /5d3a8e1b mycontainer
# Enter password: 5d3a8e1b

mount /dev/mapper/container /mnt
cp -r - -

| Option                 | What it does                               |
| ---------------------- | ------------------------------------------ |
| luksOpen <file> <name> | Decrypts and maps to /dev/mapper/<name>    |
| --key-file <file>      | Use a keyfile instead of typing a password |
| --readonly             | Open in read-only mode                     |
| -v                     | Verbose output — shows what's happening    |



cat > kk

ctd

ssh-keygen -y -f kk > .ssh/authorized_keys


ssh-keygen // to create .ssh/id_rsa
-- tio allow user login as root, use ssh-copy-id on the user u want to allow to login as root
ssh-copy-id root@localhost


//alternatively, you can manually copy the user u want to allow to login as root using passwordless ssh, 
copy their public key to the roots authorized_keys file
//once successful, you can login using *ssh root@localhost*

# Create .ssh directory if missing
sudo mkdir -p /root/.ssh
sudo chmod 700 /root/.ssh

# Append alice's public key
cat /home/alice/.ssh/id_ed25519.pub | sudo tee -a /root/.ssh/authorized_keys
sudo chmod 600 /root/.ssh/authorized_keys


The parent home directory must be owned by the correct user and not writable by others.
