WRK installation (https://github.com/wg/wrk)
```
sudo apt-get install build-essentials  libssl-dev git unzip -y
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