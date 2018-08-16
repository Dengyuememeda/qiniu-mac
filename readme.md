# qiniu-imgup-mac

## 简介
qiniu-imgup-mac是一个Mac系统下的七牛云图片上传工具，目标是简化MarkDown写作中的贴图的繁琐步骤。
qiniu-imgup-mac可以快速将剪贴板中的图片上传至七牛云，并返回MarkDown格式的链接至剪贴板。
适用人群：使用七牛云做为图床的MarkDown编写者。
平台：macOS  （macOS 10.12测试通过）

另有Linux版本，请移步：[https://github.com/xiiiblue/qiniu-imgup-linux.git](https://github.com/xiiiblue/qiniu-imgup-linux.git)

## 使用方法介绍
在编写MarkDown文档时，如果使用七牛云做图床，插入一张图片需要以下几个繁琐的步骤：
1. 截图
2. 保存为文件
3. 打开浏览器，在七牛云后台上传图片
4. 复制图片的HTTP URL
5. 在编辑器中将URL拼接为MarkDown的链接格式
6. 粘帖链接

qiniu-imgup-mac将整个操作简化为了3个快捷键操作：
1. `cmd+shift+ctrl+4`  -  截图到剪贴板
2. `cmd+shift+u`  -  使用自定义热键，上传并获取MarkDown链接
3. `cmd+v`  -  粘帖MarkDown链接

## 安装与配置
1. 安装依赖
```
pip install -r requirement.txt
```
2. 配置`config.py`，填入七牛云的AK、SK等参数
3. 使用Automator将shell脚本uimg封装为APP
![](http://oh0ra6igz.bkt.clouddn.com/k6cwa.jpg)
4. 在系统设置中（System Preference->Keyboard->Shortcuts->App Shortcuts），为APP分配快捷键
![](http://oh0ra6igz.bkt.clouddn.com/oknvx.jpg)

### 吐槽
1. 千万不要建虚拟环境   直接pip安装，并且确认`python`好环境，使用`which python`查看下你python的地址
2. 复制python地址，将`uimg`脚本中的python3环境换掉
3. AK和SK确保填写正确， 开始图片名为测试的默认名 不需要更改
4. 测试不成功的话建议直接将config文件的内容粘贴至`uimg.py`文件内
5. Automator为mac自带软件  不需要安装， 编译运行方法： 打开后 新建文稿-》选择应用程序-》搜索`运行shell`-》拖至右边-》将uimg的绝对路径粘贴到控制台中-》点击右上方run按钮
6. 测试成功后ctrl+s保存
7. 为打包好的应用配置快捷键，如果配置不成功，还是用`Automator`软件
<img src="http://qiniu.s001.xin/20c2n.jpg">
<img src="http://qiniu.s001.xin/k4n0y.jpg">
