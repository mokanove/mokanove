# A general tutorial for compiling luci-app.
## First, you need to prepare a Linux environment.
> And some free softwares.
>
> Demonstration system: Arch Linux
```
sudo pacman --needed 
```
## Download the SDK source code.
```
curl -LO https://immortalwrt.kyarucloud.moe/releases/24.10.4/targets/x86/64/immortalwrt-sdk-24.10.4-x86-64_gcc-13.3.0_musl.Linux-x86_64.tar.zst
In China? Let's try it:
curl -LO https://mirrors.cernet.edu.cn/immortalwrt/releases/24.10.4/targets/x86/64/immortalwrt-sdk-24.10.4-x86-64_gcc-13.3.0_musl.Linux-x86_64.tar.zst
```

## Unzip the compressed file
```
tar -xvf immortalwrt-sdk-24.10.4-x86-64_gcc-13.3.0_musl.Linux-x86_64.tar.zst
```
## Init SDK
> Please ensure your Git can connect to GitHub and clone successfully.
```
./scripts/feeds update -a && ./scripts/feeds install -a
```
## Locate the package directory and clone the project source code.
```
cd immortalwrt-sdk-24.10.4-x86-64_gcc-13.3.0_musl.Linux-x86_64/package/
git clone [URL]
```
## Wake up!
> Please prepare the project source code and dependencies first, and locate the SDK root directory.
```
make package/luci-app-oplist/compile V=s -j$(nproc)
```
## Done
```
cd bin/packages/x86_64/base/
```
