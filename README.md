# ipic-win
## 0x00
作为一个windows用户，写博客的时候，图片和文件是直接放到博客的另一个文件夹里面，这个对博客迁移很不方便（其实我是准备从jekyll转到hexo觉得图片不好处理）

很早之前就想做一个图片自动生成短链的工具，无奈拖沓，今晚终于开始动手了，其实挺简单的，晚上十一点开始写，凌晨一点就写好了，两个小时搞定 ;)
## 0x01 使用
1. 搭建环境
```
pip install qiniu
```
同时根据你的python的版本安装,安装 python32
```
https://sourceforge.net/projects/pywin32/files/pywin32/Build%20217/
```



2. 将你的七牛云账户的token填到对应的位置, 修改bucket的名字

3. 任意找一个截屏工具， 自带的`snippingtools`或者qq之类的，截屏。 运行该程序，该程序会自动将文件保存到七牛云，然后将markdown格式的图片链接放到剪切板， 粘贴即可


等有空的时候（意思是不想继续干了）写一个监听，截屏之后按快捷键触发上传


## 0x02
这个是在写博客的时候生成markdown的，思路很简单，当截屏的时候回把图像放到剪切板，这时候启动程序就会使用`win32api`读取剪切板内容，然后本地保存一份，接着上传到七牛云，然后上传成功就将markdown格式的链接直接放到剪切板，`Ctrl + v`， 粘贴就行

## 0x03 
另一个 `upload_tempfile`是将文件暂存到七牛云的，修改token和bucket之后即可
```
python upload_tempfile.py filename
```
稍后会打印出地址。

2017年7月9日01:30:07

赶紧睡觉，又修仙了
