# A general tutorial for compiling luci-app.
## First, you need to prepare a Linux environment.
> WARN : NEVER RUN MAKE AS ROOT
>
> This guide only support X86 immortalwrt arch SDK , if you need the other arch , do it yourself
>
> Demonstration system: Arch Linux
```
sudo pacman -Syu --needed base-devel git gawk ncurses openssl zlib \
    wget curl unzip python3 python-setuptools fillup rsync \
    libxslt libxml2 boost findutils
```
> OR any pm you love.
## Download the SDK source code.
```
curl -LO https://immortalwrt.kyarucloud.moe/releases/25.12.0-rc1/targets/x86/64/immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64.tar.zst
```
> OR ANY OTHERS MIRRORS LIKE mirrors.cernet.edu.cn

[All the mirros of immortalwrt](https://immortalwrt.kyarucloud.moe/acknowledgements.html)
## Unzip the compressed file
```
tar -xvf immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64.tar.zst
```
## Init SDK
```
cd immortalwrt-sdk-25.12.0-rc1-x86-64_gcc-14.3.0_musl.Linux-x86_64
make defconfig
./scripts/feeds update -a && ./scripts/feeds install -a
```
## Locate the package directory and clone the project source code.
```
cd package/
git clone [URL]
```
## Wake up! My baby.
```
cd ../../
make package/project-directory-name/compile V=s -j$(nproc)
```
## Done
```
cd bin/packages/x86_64/base/
# .apk at here
```
