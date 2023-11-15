# VPS-BenchMark
A Breif Instruction Set on Benchmarking a Newly Configured Linux VPS.

This Repository can come in handy for Sysadmins/Users that are trying to measure and benchmark the performance of their newly bought/rented Linux Server.

**TL;DR -->**
List of the commands/scripts mentioned:
 1. Bench.sh
 2. UnixBench.sh
 3. dd
 4. YABS
 5. ioping
 6. NetData
 7. Traceroute
 8. SpeedTest-Cli

----
## **1. Bench.sh**
   - Used to test CPU, memory, disk IO, as well as VPS network speed and latency.
>     $ git clone https://github.com/ServerKite/bench.sh.git && cd bench.sh && chmod +x bench.sh && bash bench.sh
     
     

## **2. UnixBench.sh**
   - Used to test system calls, reading and writing, processes, graphical tests, 2D, 3D, pipelines, operations, C libraries and other system benchmark performance to provide test data.
>     $ git clone https://github.com/chuckleb/Linux-Bench/blob/master/linux-bench.sh && cd linux-bench.sh && chmod +x linux-bench.sh && bash linux-bench.sh

     

## **3. dd**
   - Used to benchmark disk read/write speed and CPU performance
     # Disk write speed (1GB, 1M Block Size):
     >     $     dd if=/dev/zero of=tmpfile bs=1M count=1024 conv=fdatasync

     # Disk read speed
     1. Delete Buffer Cache:
     >     $    sudo /sbin/sysctl -w vm.drop_caches=3
     2. Read tmpfile (Created in Writing Section)
     >     $    dd if=tmpfile of=/dev/null bs=1M count=1024
     3. Delete tmpfile after testing:
     >     $    rm tmpfile
 
   CPU Bench
   >     $  dd if=/dev/zero bs=1M count=1024 | md5sum
  # *** A minimum of 300MB/s is accpeted, lower means --> Bad Performance, Probably an overloaded CPU or Limited CPU Core Performance Allowance From Host.
   


## **4. YABS (Yet Another Benchmark Script)**
   - Used to run fio, iperf3 and geekbench scripts.
     >     $ wget -qO- yabs.sh | bash


## **5. ioping (I/O Latency checking)**
   - Simple tool used to measure disk's read/write performance.
   >     $  sudo apt install ioping;ioping


## **6. NetData**
   - Powerful Monitoring Tool used as an alternative to Prometheus and vise versa.
     Check Documentation: github.com/netdata/netdata


## **7. Traceroute**
   - Used to Trace routing path of VPS + measuring network latency.
     Tracing google.com:
   >     $   sudo apt install traceroute; traceroute google.com


## **8. SpeedTest-Cli**
   - The Famous Ookla Website. Used for measuring Download/Upload Speeds + Ping and Jitter
   >     $   curl -s https://packagecloud.io/install/repositories/ookla/speedtest-cli/script.deb.sh | sudo bash
     $ sudo apt install speedtest
