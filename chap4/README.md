```bash
free
chmod +x memuse.py 
./memuse.py 
free

chmod +x buff-cache.sh 
./buff-cache.sh 
sar -r 1 5
ps aux

go build segv.go 
./segv 
make segv-c
./segv-c

go build mmap.go 
./mmap 

chmod +x demand-paging.py 
./demand-paging.py 
sar -r 1
sar -B 1

chmod +x capture.sh 
./demand-paging.py 
./capture.sh 
sar -r ALL 1
```
