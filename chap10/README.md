```bash
egrep -c '^flags.*(vmx|svm)' /proc/cpuinfo 

virt-install --name ubuntu2004 --vcpus 1 --cpuset=0 --memory 4096 --os-variant ubuntu20.04 --graphics none --extra-args 'console=ttyS0 --- console=ttyS0' --location http://us.archive.ubuntu.com/ubuntu/dists/focal/main/installer-amd64/
virsh domifaddr ubuntu2004 
virsh start ubuntu2004 
virsh list
ps ax | grep qemu-system

# 仮想環境のターミナルでSSHサーバーを起動する、その後ホストでもSSHサーバーを起動すればSCPでｊｐｇなどのファイルを転送できる
ssh kazuho@192.168.122.165

sudo apt-get install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh

sar -P 0 1
top
chmod +x inf-loop.py 
taskset -c 0 ./inf-loop.py &
sar -P 0 1 1
top
kill 65770

taskset -c 0 ./inf-loop.py
```
