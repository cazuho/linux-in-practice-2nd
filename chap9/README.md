```bash
fio --name test -readwrite=randread --filename testdata --filesize=1G --size=4M --bs=4K --output-format=json
rm testdata 
cat /sys/block/sda/queue/scheduler 
```
