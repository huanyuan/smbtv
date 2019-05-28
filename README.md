# smbtv
假如手機有 root 的話,  
服務器位址那邊填入手機 ip + name directory
ex: 192.168.1.101/sdcard
就可以瀏覽手機內檔案, 想要放照片或影片都沒有問題

 如果手機沒有 root 的話, 需要在 url 上多加 port number
samba protocol 預設是使用 445 port,
但是因為安全性的關係 android 不讓 app 使用這個 port
所以沒 root 的手機會看到 samba server 使用的是 7777 port
所有必須使用以下的 url 形式
192.168.1.101:7777/sdcard

沒有 root 的手機用 ES 檔案瀏覽器可以播放照片沒有問題
但是播放影音檔時就不行了, 猜測是 ES 瀏覽器的 bug

不過 bs player 有支援瀏覽區網, 所以可以用 bs player 連進手機
在 bs player 的瀏覽區網模式用以下 url 
 192.168.1.101:7777/sdcard
就可以瀏覽手機內的檔案並撥放

要用 mx player 的話 

可以利用 ES 瀏覽器的 http streaming server
首先不要退出 ES 瀏覽器, 讓 ES保持連進手機的狀態
然後打開網路瀏覽器, 在網址列輸入下列 url

http://127.0.0.1:59777/smb/手機ip@手機ip:7777/name directory/file path

ex:
http://127.0.0.1:59777/smb/192.168.1.101@192.168.1.101:7777/sdcard/xxx/yyy.mkv

此時會跳出提示選擇 app 來播放影片, 再選 mx player 就可以了

SMBTV is a simple SMB server for Android TV based on [JLAN](https://www.alfresco.com/news/press-releases/alfresco-makes-leading-java-implementation-jlan-shared-file-drive-interface)

![Home of SMBTV](http://vpictu.re/uploads/0e14a5d6165fcb2903cd227abe7da89533debb29.png)
