```bash
ls /sys/fs/cgroup
sudo su
mkdir /sys/fs/cgroup/cpu/test
ls /sys/fs/cgroup/cpu/test/
cat /sys/fs/cgroup/cpu/test/cpu.cfs_period_us 
cat /sys/fs/cgroup/cpu/test/cpu.cfs_quota_us 
./inf-loop.py &
echo 81360 > /sys/fs/cgroup/cpu/test/tasks
cat /sys/fs/cgroup/cpu/test/tasks 
top -b -n 1 | head
echo 50000 > /sys/fs/cgroup/cpu/test/cpu.cfs_quota_us 
top -b -n 1 | head
kill 81360
rmdir /sys/fs/cgroup/cpu/test 
```
