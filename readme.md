
1. madmax plotter编译

```
git clone https://github.com/madMAx43v3r/chia-plotter
cd chia_plotter
git submodule update --init

sudo apt install -y libsodium-dev cmake g++ git build-essential
/make_devel.sh

```

在编译过程中，会下载新的库，如果报错，根据提示执行 "git config --global --add safe.directory ... " 即可解决问题

在build目录下，生成了chia_plot，即是所要的可执行文件。

2. plot文件

2.1 首先创建文件夹和映射内存

```
cd plotting
mkdir ram
mkdir tmp
mkdir final
sudo mount -t tmpfs -o size=112G tmpfs ./ram/
```

2.2 重要信息

farmer_key: 0x83a2c8b05746d13e9d396c5724936f3a1d4376de8a4a0451331d903956c5154711c395a06b939197bbd24092109b324b 
pool_key: 0xaab0fee7f870052302ac3878de7e2f1833363e045a9d98104bf7fdb6b1917a33eb10c52bfc5124c63e47374306ff26d0

2.3 运行chia_plot软件

可以生成hpool og文件
注意： 目录后面一定要加/, key不能带0x

```
./chia_plot -n 1 -t ./tmp/ -2 ./ram/ -d ./final/ -f <farmer_key> -p <pool_key>
nohup ./chia_plot -n 50 -t ./tmp/ -2 ./ram/ -d ./final/ -f 83a2c8b05746d13e9d396c5724936f3a1d4376de8a4a0451331d903956c5154711c395a06b939197bbd24092109b324b -p aab0fee7f870052302ac3878de7e2f1833363e045a9d98104bf7fdb6b1917a33eb10c52bfc5124c63e47374306ff26d0 &
```

也可以生成hpool pp文件

```
./chia_plot -n 1 -t ./tmp -2 ./ram -d ./final -f <farmer_key> -c <pool_contract_address>
```




