WRK installation (https://github.com/wg/wrk)
```
sudo apt-get install build-essential libssl-dev git unzip -y
git clone git@github.com:wg/wrk.git
cd wrk
sudo make
sudo cp wrk /usr/local/bin
```

Check wrk version
```
wrk -v
```

To run wrk
```
wrk -t12 -c400 -d30s http://<url><:port>
#-t number of threads
#-c number of requests
#-d time (s means seconds)
```

Benchmark
Before Octane
wrk -t12 -c500 -d5s http://localhost
```
Running 5s test @ http://localhost
  12 threads and 500 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   997.76ms  559.06ms   1.95s    57.89%
    Req/Sec    30.05     18.38    60.00     45.95%
  243 requests in 5.06s, 4.35MB read
  Socket errors: connect 0, read 243, write 0, timeout 148
Requests/sec:     48.03
Transfer/sec:      0.86MB
```

Octane Swoole
```
Running 5s test @ http://localhost
  12 threads and 500 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.32s   435.70ms   1.97s    76.91%
    Req/Sec    35.40     31.38   212.00     81.17%
  1520 requests in 5.07s, 27.14MB read
  Socket errors: connect 0, read 0, write 0, timeout 17
Requests/sec:    299.82
Transfer/sec:      5.35MB
```

Octane RoadRunner
```
Running 5s test @ http://localhost
  12 threads and 500 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency     1.57s   501.30ms   2.00s    85.29%
    Req/Sec    27.28     24.38   180.00     84.10%
  1111 requests in 5.10s, 19.84MB read
  Socket errors: connect 0, read 0, write 0, timeout 275
Requests/sec:    217.78
Transfer/sec:      3.89MB
```
