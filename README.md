### 1.安装lrzsz
```
brew install lrzsz
```

### 2.将两个sh 脚本保存在 /usr/local/bin/
拉取 https://github.com/wangyafei6610/item2-sh 两个sh文件，将他们拷贝到/usr/local/bin文件夹中。
```
sudo cp ./item2-sh/iterm2-* /usr/local/bin
```

### 3.配置iterm2属性

#### 打开配置文件
item2-->Preferences-->profiles-->Default--->Advanced--->Triggers--->Edit

#### 在iTerm 2添加Triggers
Regular expression: rz waiting to receive.\*\*B0100
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-send-zmodem.sh

Regular expression: \*\*B00000000000000
Action: Run Silent Coprocess
Parameters: /usr/local/bin/iterm2-recv-zmodem.sh


至此，所有配置完成。下面就可以使用黑科技来传输文件了。
使用方法
将文件传到远端服务器
在远端服务器上输入 rz ，回车
选择本地要上传的文件
等待上传
从远端服务器下载文件
在远端服务器输入 sz filename filename1 ... filenameN
选择本地的存储目录
等待下载
PS:远端服务器也需要安装lrzsz。centOS安装方法： yum -y install lrzsz

FROM:https://www.jianshu.com/p/e6700c50fced
