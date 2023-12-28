
1. madmax plotter编译

```
git clone https://github.com/madMAx43v3r/chia-plotter
cd chia_plotter
git submodule update --init

sudo apt install -y libsodium-dev cmake g++ git build-essential
/make_devel.sh

```

在编译过程中，会下载新的库，如果报错，通过提示执行 "git config --global --add safe.directory ... " 解决问题

