# frida
## frida.js为算法自吐脚本
```
用法:
frida -U -f app运行名 -l E:\Cyber_Security_Tools\信息收集\脚本和poc\frid.js
```
## 绕过脚本用法
```
设置burp证书
先在burp里设置本机代理
访问代理地址并下载burp证书
将下载的burp证书导入到手机中/data/local/tmp目录下，并重命名为cert-der.crt（此名称在接下来的fridascript.js脚本中使用，如果该名字命名为其他则脚本中相对应的地方也需要进行替换）
adb push cacert.der /data/local/tmp/cert-der.crt
模拟器设置代理，在安卓手机设置->wlan选择对应网络设置代理
打开你想抓包的软件，使用frida-ps -U命令列出设备上运行的服务，找到对应的包名
在本地新建一个js文件，并将一下内容写入
脚本里的30行其中对应的就是burp证书的信息
将fridascript.js注入到目标应用程序中
frida -U -f com.xxxx.app.ui -l C:\Users\xxx\Desktop\fridascript.js
```
