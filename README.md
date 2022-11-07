# DST dedicate server setup with cave

1. Create 2 free aws ami instance(1 for master, 1 for cave)

2. ssh using putty

3. setup environment

```
sudo yum update -y
sudo yum install glibc.i686 libstdc++.i686 libcurl4-gnutls-dev.i686 libcurl.i686 screen -y
```

4. download steam

```
mkdir ~/steamcmd
cd ~/steamcmd
wget https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz
tar -xvzf steamcmd_linux.tar.gz
./steamcmd.sh
```

5. download dst server

```
login anonymous
force_install_dir ../dst_server
app_update 343050 validate
quit
```

6. create save folder
```
mkdir -p ~/.klei/DoNotStarveTogether
```

7. use scp to move save folder

8. fix library

```
cd ~/dst_server/bin/lib32
ln -s /usr/lib/libcurl.so.4 libcurl-gnutls.so.4
```

9. start server

```
sh dst_server/bin/restart_cave.sh
sh dst_server/bin/restart_master.sh
```
