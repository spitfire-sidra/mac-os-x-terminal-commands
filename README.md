mac-os-x-terminal-commands
==========================


複製資料夾

```
ditto -V /old/folder/ /new/folder/
```


列出隱藏資料夾

```
defaults write com.apple.finder AppleShowAllFiles -bool TRUE
killall Finder
```


在預覽模式中啟用選取功能(Enable Text Selection in Quick Look)

```
defaults write com.apple.finder QLEnableTextSelection -bool TRUE
killall Finder
```


列出所有網路界面(Network Interfaces)

```
ifconfig -a
```


列出預設閘道(Default Gateway)

```
route -n get default
```


列出路由表(Routing Table)

```
netstat -rn
```


取得網路界面 en0 的IP位址

```
ipconfig getifaddr en0
```


將網路界面 en0 設定成 DHCP

```
sudo ipconfig set en0 DHCP
```


列出 I/O 裝置

```
diskutil list
```


卸載(unmount) I/O 裝置

```
sudo distkutil unmountDisk /dev/disk<number>
```


讓系統不要進入休眠

```
caffeinate
```


讓系統20秒內不要進入休眠

```
caffeinate -u -t 20
```


讓系統用英文念一段句子(聽英文發音好用)

```
say "We love Mac OS X"
```
