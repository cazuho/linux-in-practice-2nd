```bash
chmod +x cow.py 
./cow.py

chmod +x non-shared-memory.py 
./non-shared-memory.py 
chmod +x shared-memory.py 
./shared-memory.py 

free | awk '(NR==2){print $2}'

touch count
echo 0 > count
cat count
chmod +x inc.sh 
./inc.sh 
cat count
echo 0 > count
for ((i=0;i<1000;i++)) ; do ./inc.sh ; done
cat count
echo 0 > count
for ((i=0;i<1000;i++)) ; do ./inc.sh & done; for ((i=0;i<1000;i++)); do wait+ done
cat count

echo 0 >count 
chmod +x inc-wrong-lock.sh 
for ((i=0;i<1000;i++)) ; do ./inc-wrong-lock.sh & done; for ((i=0;i<1000;i++)); do wait; done
cat count 

chmod +x inc-lock.sh 
echo 0> count 
touch lock
for ((i=0;i<1000;i++)) ; do ./inc-lock.sh & done; for ((i=0;i<1000;i++)); do wait; done
cat count 

ps -eLF
```
