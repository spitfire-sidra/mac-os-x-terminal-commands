mac-os-x-terminal-commands
==========================

用行寬 72 印出檔案內容

```
fold -w 72 file.txt
```

搜尋 Whatis 資料庫中的字串

```
apropos <keywords>
```

看檔案的擴充屬性(extended attributes)

等同於 [lsattr](http://linux.vbird.org/linux_basic/0220filemanager.php#lsattr)

```
$ ls -leO@ file
-rw-r--r--  1 user  staff  uchg 675 12 23 11:33 /Users/user/file
```

`uchg` 就是擴充屬性 `unchangeable`

```
e -> Print the Access Control List (ACL) associated with the file, if present, in long (-l) output.

@ -> Display extended attribute keys and sizes in long (-l) output.

O -> Include the file flags in a long (-l) output.
```

改變檔案的擴充屬性(extended attributes)

等同於 [chattr](http://linux.vbird.org/linux_basic/0220filemanager.php#chattr)

```
$ chflags <flags> <file>
```

例如:

```
$ chflags uchg file
```


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

同意 MAC OS X Xcode/iOS 使用條款

```
sudo xcodebuild -license
```

## 剪貼簿操作

複製檔案內容到剪貼簿

```
$ pbcopy < my-test-file.txt
```

or

```
$ ls ~ | pbcopy
```

從剪貼簿貼上內容

```
pbpaste
```

## 雜湊值計算

從 CONSOLE 輸入算 SHA1

```
$ shasum -a 1 -
<隨便輸入，按 CTRL+D 結束輸入>
```

note: -a {1, 244, 256, 384, 512, 512224, 512256}


從二進制檔案算 SHA1

```
$ shasum -a 1 -b file.bin
```

從文字檔算 SHA1

```
$ shasum -a 1 -t file.txt
```

## 網路指令

觀察 TCP 連線情況

```
$ nettop -m tcp
```

清除 DNS 快取

```
# Yosemite
$ sudo discoveryutil mdnsflushcache

# Mavericks, Mountain Lion and Lion
$ sudo killall -HUP mDNSResponder
```

## Reference

https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/index.html

https://support.apple.com/en-us/HT202516
