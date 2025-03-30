```bash
ls -l /dev/
ps ax | grep bash
echo hello >/dev/pts/0
ps ax | grep bash
echo hello >/dev/pts/1

# 書籍と異なり/mntではなくmntとなることに注意
fallocate -l 1G loopdevice.img
sudo losetup -f loopdevice.img 
losetup -l
sudo mkfs.ext4 /dev/loop9
mkdir mnt
sudo mount /dev/loop9 mnt
mount
sudo chown -R $USER:$USER mnt
echo "hello world" > mnt/testfile
ls mnt
cat mnt/testfile 
sudo umount mnt
sudo strings -t x /dev/loop9
echo "HELLO WORLD" > testfile-overwrite
cat testfile-overwrite 
sudo dd if=testfile-overwrite of=/dev/loop9 seek=$((0x8200000)) bs=1
sudo mount /dev/loop9 mnt
ls mnt
cat mnt/testfile 
sudo umount mnt
sudo hexdump -C /dev/loop9
rm loopdevice.img 
rm testfile-overwrite 
rm -rf mnt/

cat /proc/interrupts 
while true ; do grep Local /proc/interrupts ; sleep 1 ; done

ls -l /dev/sda
ls -l /dev/disk//by-path/
ls -l /dev/disk//by-path/pci-0000\:04\:00.0-ata-1 
cat /etc/fstab 
history | tail -n 60 | cut -c 8- >> README.md
```
