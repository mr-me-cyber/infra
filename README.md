# infra

ssh-keygen
ssh-copy-id root@localhost

exit
find <dir> down
-perm /1000
-not -user bob



setfacl -m+ -b all -x -
setfacl -m u:operator:rw mess.txt
setfacl -b mess.txt
setfacl -m u:operator:r file
setfacl -x u:bob /root/199306.txt
setfacl -b /root/199306.txt
after to ensure nobodyu can access file
chmod 000 /root/199299.key
setfacl -m u:alice:r-x /root/script.sh
setfacl -m m::r-- file.tx


chown u:g .txt

dd if= of= bs= count=

getfacl

cryptsetup luksFormat /dev/sdc1
cryptsetup luksOpen /dev/sdc1 x
mk.xfs /dev/mapper/x
umount /mnt/
mount /dev/mapper/x /mnt

/////////////////////////////////////////////
\n 


Layer 0:  Regular file on disk
          /5d3a8e1b  (40MB file, contains LUKS header + encrypted data)
               │
               │  losetup -f /5d3a8e1b
               ▼
Layer 1:  Loop device  ← "pretend this file is a disk"
          /dev/loop0
               │
               │  cryptsetup luksOpen /dev/loop0 mycontainer
               ▼
Layer 2:  Mapper device  ← "decrypt everything passing through here"
          /dev/mapper/mycontainer
               │
               │  mount /dev/mapper/mycontainer /mnt
               ▼
Layer 3:  Mounted filesystem
          /mnt/  ← you see your files here normally


What do you have?
        │
        ├─── A real partition (/dev/sdb1, /dev/sdc)?
        │           │
        │           ├── Is it LUKS encrypted?
        │           │       ├── YES → cryptsetup luksOpen → /dev/mapper/x → mount
        │           │       └── NO  → mkfs / mount directly
        │           │
        │
        └─── A plain FILE (/5d3a8e1b, disk.img)?
                    │
                    ├── Just need to format/mount it?
                    │       └── losetup → /dev/loop0 → mkfs → mount /dev/loop0
                    │
                    └── It's LUKS encrypted?
                            └── losetup → /dev/loop0
                                    └── cryptsetup luksOpen → /dev/mapper/x
                                                └── mount /dev/mapper/x



fdisk /dev/sdc --not here, when creating new partition on disk


losetup -f --show /af90u09ua
cryptsetup luksOpen /dev/loop0 loop
mount /dev/mapper/loop0 /mnt
ls /mnt
cp /mnt/?? /root

mount | grep /mnt 



losetup -f /efajh2332
lsblk -f
cryptsetup luksOpen /dev/loop0 container

mount /dev/mapper/container /mnt
cp /mnt/* /root


fdisk /dev/sdc
n p w
mkfs.ext2 /dev/sdc1
mount -o ro /dev/sdc1 /mnt

openssl aes-128-cbc -d -K -iv -in -out
openssl rsa -in keyfile -pubout > keyfile.pub


openssl dgst -sha256 -verify  -signature //
openssl dgst -sha256 -sign (private)  -out   file
openssl dgst -sha256 -verify public  -signature (.sign file)   file

openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:2014 -out 
rsa -noout -text -in


openssl rsa -in keyfile -pubout > keyfile.pub
openssl rsautl -decrypt -in /root/17099.enc -inkey keyfile > /root/17099.txt
openssl pkeyutl -decrypt -in /root/17099.enc -inkey keyfile -out /root/17099.txt


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
