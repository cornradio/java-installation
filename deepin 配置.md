# deepin安装后的配置

[添加控制中心快捷键](#添加控制中心快捷键) |
[把文件浏览器换成默认](#把文件浏览器换成默认) |
[配置electron-ssr](#配置electron-ssr) |
[设置谷歌浏览器和vscode的外观](#设置谷歌浏览器和vscode的外观) |
[创建桌面快捷方式](#创建桌面快捷方式)
[搞主题](#搞主题) | 
## 时间的校准
时间和windows会冲突，要改[时间校准配置](https://blog.csdn.net/White_Idiot/article/details/78039660)

```
sudo apt-get install ntpdate
sudo ntpdate time.windows.com
sudo hwclock --localtime --systohc
```

## 添加控制中心快捷键

把下面的代码放进`设置-键盘和语言-快捷键-自定义`里面，并且自定义快捷键

打开设置面板
```
dbus-send --print-reply --dest=com.deepin.dde.ControlCenter /com/deepin/dde/ControlCenter com.deepin.dde.ControlCenter.Show
```

旋转屏幕
```
 xrandr -o left
 xrandr -o right
 xrandr -o inverted
 xrandr -o normal
```
## 把文件浏览器换成默认

在安装vscode之后，默认的文件浏览器会变成vscode，不好用，所以要换回去。
在控制台` ctrl+alt+T `里面执行以下的代码。
```
xdg-mime default dde-file-manager.desktop inode/directory
```
## 配置electron-ssr

使用谷歌是必然的选择，所以我需要设置代理。deepin设置代理的办法还是很简单的。
1. 左键electron-ssr-复制ttp代理设置
2. 打开设置-网络-系统代理-自动
3. 粘贴配置url
4. 重启浏览器生效

## 设置谷歌浏览器和vscode的外观

### chrome
1. 地址栏输入`chrome://settings/appearance`
2. 关闭 使用系统标题栏和边框

### vscode
1. 搜索 `Title bar Style`
2. 更改为 `custom`

## 创建桌面快捷方式
1. 创建一个文本文件如下格式
2. 后缀名自改成 `desktop`
```
[Desktop Entry]
Version=1.0
Type=Application
Terminal=false
Icon=someicon               //这里填写图标的目录
Exec=sh /path/to/studio.sh  //这里再“sh ”的右边填写studio.sh的目录
Name=Android Studio
```
## 安装字体
[firacode](https://github.com/tonsky/FiraCode)

## 搞主题
[deepin官方教程](https://wiki.deepin.org/wiki/%E8%87%AA%E5%AE%9A%E4%B9%89%E4%B8%BB%E9%A2%98)

## 软件下载
[vscode](https://code.visualstudio.com/) |
[chrome](https://www.google.com/chrome/) |

[gitkraken](https://www.gitkraken.com)
## 必装的一些软件--v控制台安装
java ：
`apt-get install default-jdk`

git ：
`apt install git`

c/c++ :
gcc g++ gdb 
