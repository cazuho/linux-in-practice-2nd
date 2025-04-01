```bash
chmod +x plot-cache.py 
go build cache.go 
./cache 

dd if=/dev/zero  of=testfile oflag=sync bs=1G count=1
dd if=/dev/zero  of=testfile bs=1G count=1
free
sudo su
echo 3 > /proc/sys/vm/drop_caches 
free
dd if=testfile of=/dev/null bs=1G count=1
dd if=testfile of=/dev/null bs=1G count=1
rm testfile 

sysctl vm.dirty_writeback_centisecs 
sysctl vm.dirty_background_ratio 
sysctl vm.dirty_ratio 

free
dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct,sync 
free

sar -r 1
sar -B 1
swapon --show
free 
sar -W 1
sar -S 1
```
