
# Visual Studio 2017 community
Note: install .net framework 4.0 & WindowSDK 7.1 (xmr/jaxmr-lib/winsdk_web.exe)
- cd jaxmr
- mkdir build
- cd build
- cmake .. -G "Visual Studio 15 2017 Win64" -T v140_xp -DCMAKE_BUILD_TYPE=Release  -DUV_INCLUDE_DIR="xmr\jaxmr-lib\libuv-msvc2017-x64\include" -DUV_LIBRARY="xmr\jaxmr-lib\libuv-msvc2017-x64\lib\libuv.lib"
 
after run cmake, it will generate the visual studio project file on build folder.
- open xmrig.sln: change from debug to release then build

--> Done


# using libuv-gcc-x64
Note: Install cmake 3.9+
- cd jaxmr
- mkdir build
- cd build
- cmake .. -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Release -DUV_INCLUDE_DIR="xmr\jaxmr-lib\libuv-gcc-x64\include" -DUV_LIBRARY="xmr\jaxmr-lib\libuv-gcc-x64\lib\libuv.a"
- make

# Options
```
  -a, --algo=ALGO       cryptonight (default) or cryptonight-lite
  -o, --url=URL         URL of mining server
  -O, --userpass=U:P    username:password pair for mining server
  -u, --user=USERNAME   username for mining server
  -p, --pass=PASSWORD   password for mining server
  -t, --threads=N       number of miner threads
  -v, --av=N            algorithm variation, 0 auto select
  -k, --keepalive       send keepalived for prevent timeout (need pool support)
  -r, --retries=N       number of times to retry before switch to backup server (default: 5)
  -R, --retry-pause=N   time to pause between retries (default: 5)
      --cpu-affinity    set process affinity to CPU core(s), mask 0x3 for cores 0 and 1
      --cpu-priority    set process priority (0 idle, 2 normal to 5 highest)
      --no-huge-pages   disable huge pages support
      --no-color        disable colored output
      --donate-level=N  donate level, default 5% (5 minutes in 100 minutes)
      --user-agent      set custom user-agent string for pool
  -B, --background      run the miner in the background
  -c, --config=FILE     load a JSON-format configuration file
  -l, --log-file=FILE   log all output to a file
      --max-cpu-usage=N maximum CPU usage for automatic threads mode (default 75)
      --safe            safe adjust threads and av settings for current CPU
      --nicehash        enable nicehash support
      --print-time=N    print hashrate report every N seconds
  -h, --help            display this help and exit
  -V, --version         output version information and exit
```

## Algorithm variations
Since version 0.8.0.
* `--av=1` For CPUs with hardware AES.
* `--av=2` Lower power mode (double hash) of `1`.
* `--av=3` Software AES implementation.
* `--av=4` Lower power mode (double hash) of `3`.
