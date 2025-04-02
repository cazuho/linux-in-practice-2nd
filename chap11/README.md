```bash
ls -l /proc/$$/ns/pid
sudo unshare --fork --pid --mount-proc bash
echo $$
ls -l /proc/1/ns/pid
ps ax

# 別端末
pstree -p | grep unshare
sudo ls -l /proc/81061/ns/pid

pstree -p | grep unshare

# 別端末
sudo unshare --fork --pid --mount-proc bash
ls -l /proc/1/ns/pid
```
