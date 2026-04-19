# A general tutorial for compiling ImmortalWrt SDK.
## 🚀 First, you need to prepare a Linux environment.
> WARN : NEVER RUN MAKE AS ROOT
>
> Demonstration system: Arch Linux
```
sudo pacman -Syu --needed base-devel make git gawk ncurses openssl zlib \
    wget curl unzip python3 python-setuptools fillup rsync \
    libxslt libxml2 boost findutils gcc g++ unzip patch
```
> OR any pm you love.
## ⏬ Download the SDK source code.
[All the mirros of immortalwrt](https://downloads.immortalwrt.org/acknowledgements.html)
```
curl -LO https://downloads.immortalwrt.org/releases/25.12.0-rc1/targets/x86/64/immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64.tar.zst
```
## 📦 Unzip the compressed file
```
tar -xvf immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64.tar.zst
```
## 🛠 Init SDK
```
cd immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64
make defconfig
./scripts/feeds update -a && ./scripts/feeds install -a
```
## 📝 Locate the package directory and clone the project source code.
```
cd package/
git clone [URL]
```
## 🚀 Wake up! My baby.
```
cd ../../
make package/project-directory-name/compile V=s -j$(nproc)
```
## 🎉 Done
```
cd bin/packages/x86_64/base/
# .apk at here
```
