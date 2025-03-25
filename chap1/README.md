go build hello.go 
./hello
strace -o hello.log ./hello
cat hello.log 
chmod +x hello.py
strace -o hello.py.log ./hello.py 
cat hello.py.log 
sar -P 0 1 1
chmod +x inf-loop.py 
taskset -c 0 ./inf-loop.py &
sar -P 0 1 1
kill 14469
sar -P 0 1 1
chmod +x syscall-inf-loop.py 
taskset -c 0 ./syscall-inf-loop.py &
sar -P 0 1 1
kill 14605
strace -T -o hello.log ./hello
cat hello.log
ldd /bin/echo
ldd /bin/cat
ldd /usr/bin/python3
dpkg-query -W | grep ^lib
cc -static -o pause pause.c
ls -l pause
ldd pause
cc -o pause pause.c 
ls -l pause
ldd pause
ldd hello
