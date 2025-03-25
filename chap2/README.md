```bash
ps aux
ps aux --no-header | wc -l

chmod +x fork.py 
./fork.py 

chmod +x fork-and-exec.py 
./fork-and-exec.py 

cc -o pause -no-pie pause.c
readelf -h pause
readelf -S pause
./pause &
cat /proc/18548/maps
kill 18548
file pause

cc -o pause pause.c
./pause &
cat /proc/18698/maps
./pause &
cat /proc/18716/maps
kill 18698 18716

pstree -p
ps aux

chmod +x wait-ret.sh 
./wait-ret.sh

chmod +x intignore.py 
./intignore.py 
ps
kill 19899
kill -9 19899

sleep infinity &
jobs 
fg 1
ps
kill 20445
ps
kill -9 20445 20450

ps ajx
ps ajx | less
ps ajx
```
