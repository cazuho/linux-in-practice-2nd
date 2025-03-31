```bash
echo hello > testfile
vi filemap.go
go build filemap.go 
./filemap 
cat testfile 

mount | grep ^tmpfs 
free 
mkdir mnt
sudo mount -t tmpfs tmpfs mnt -osize=1G
mount | grep mnt
free 
sudo dd if=/dev/zero of=mnt/testfile bs=100M count=1
free
sudo umount mnt
free
rm -rf mnt

ls /proc/$$
strace free
ls /sys/block/
cat /sys/block/sda/dev 
ls -l /dev/sda
```
