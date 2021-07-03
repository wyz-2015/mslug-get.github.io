# Linux版模拟器获取(Ubuntu & Arch Linux)

主要介绍Ubuntu平台的模拟器。Arch系用户可浏览本页底部部分。(Arch都装成功了，想必计算机功力很不错了吧，还需要我的说明吗……)

## MAME

依次执行以下命令：

```
sudo add-apt-repository ppa:c.falco/mame
sudo apt-get update
sudo apt-get install mame
```

更新时间一般是官方版更新后的三四天后。<s>当然也有直接“翘班”，一整个月不更新的情况。</s>

## Flycast

作者没给出“deb”包，以自己编译为宜。

### 编译安装

打开“`终端`”，切入合适的目录，执行：

```
git clone --recurse-submodules https://github.com/flyinghead/flycast.git
cd flycast
cmake ./
```

执行“`cmake ./`”一步时很可能会报错，一般都是缺包问题。可以在软件包管理器中寻找并补上这些包，这些包的名字一般都是像“`lib××××-dev`”这样的。补包后再次执行这一条命令，直到不报错，当前目录下出现“`Makefile`”文件为止。

出现“`Makefile`”后不急着“`make`”。

```
cd shell/linux
make
sudo make install
```

看到程序菜单里出现“`Flycast`”时才算安装完成。

### 更新

在`flycast`目录下：

```
git pull --recurse-submodules
cd shell/linux
make
sudo make install
```

## Desmume

```
sudo apt install desmume
```

## PPSSPP(SDL)

同样是编译安装、更新。过程操作可参考上方“`Flycast`”处。

### 编译

1. `git clone --recurse-submodules https://github.com/hrydgard/ppsspp.git`
2. `cd ppsspp`
3. `./b.sh`
4. 根据报错提示补“dev”包。
5. `./b.sh`，若仍报错则返回`第4步`。
6. 编译出可执行文件后，`sudo make install`。

### 更新

```
git pull --recurse-submodules
./b.sh
sudo make install
```

## mGBA

`VBA-M`画面不好，很暗，不推荐用。

`sudo apt install mgba-qt`或`sudo apt install mgba-sdl`

## PCSXR

```
sudo apt install pcsxr
```

## PCSX2

```
sudo dpkg --add-architecture i386
sudo add-apt-repository ppa:pcsx2-team/pcsx2-daily
sudo apt update
sudo apt install pcsx2-unstable
```

## 我是用Arch Linux的！

Arch下获取软件包实在是太方便了！这里就只列出软件包名了。

* mame
* desmume
* ppsspp
* pcsx2
* mgba
* pcsxr
* flycast-git<sup>AUR</sup>
