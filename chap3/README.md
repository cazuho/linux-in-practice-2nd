```bash
chmod +x load.py 
time ./load.py 
time sleep 3

chmod +x multiload.sh 
./multiload.sh 1
./multiload.sh 2
./multiload.sh 3
./multiload.sh -m 1
./multiload.sh -m 2
./multiload.sh -m 3
time ./multiload.sh -m 2
 
chmod +x sched.py 
chmod +x plot_sched.py 
for i in 1 2 3 ; do ./sched.py $i ; done

chmod +x sched-nice.py 
./sched-nice.py 5

nice -n 5 taskset -c 0 ./inf-loop.py &
sar -P 0 1 1
kill 23240

chmod +x cpuperf.sh 
chmod +x plot-perf.py
./cpuperf.sh 8
grep -c processor /proc/cpuinfo
cat /sys/devices/system/cpu/smt/control 
echo off >/sys/devices/system/cpu/smt/control 
sudo su
./cpuperf.sh 8
echo on >/sys/devices/system/cpu/smt/control 
cat /sys/devices/system/cpu/smt/control 
grep -c processor /proc/cpuinfo
```
