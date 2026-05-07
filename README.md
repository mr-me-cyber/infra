# infra

ssh-keygen
ssh-copy-id root@localhost

exit

-perm /100
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
cryptsetup luksOpen /dev/sdc
mk.xfs /dev/mapper/x
umount /mnt/
mount /dev/mapper/x /mnt
fdisk /dev/sdc

lusetup -f /af90u09ua
cryptsetup luksOpen /dev/loop0 loop
mount /dev/mapper/loop0 /mnt
ls /mnt
cp /mnt/?? /root

openssl aes-128-cbc -d -K -iv -in -ouy

openssl dgst -sha256 -sign private  -out file
openssl dgst -sha256 -verify  -signature   file

openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:2014 -out 
rsa -noout -text -in
setfacl -m u:operator:r file

fdisk /dev/sdc
n p w
mk.ext2 /dev/sdc1
mount -o ro /dev/sdc1 /mnt

4 o
2 g
1 T

ssh-keygen -y -f k > .ssh/authorized_keys
chmod 444 authro...

Permission rules (key to avoid “Permission denied”)
~/.ssh must be 700 (drwx------)
~/.ssh/authorized_keys must be 600 (-rw-------)
The user’s private key (id_rsa) must be 600

**disk partition**
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





The parent home directory must be owned by the correct user and not writable by others.
