# 7*24小时无人在线直播脚本和配置方法 FFmpeg循环推流脚本

# 一、安装依赖包

Ubuntu/Debian系统安装
```
apt update -y && apt install vim screen -y
```
Centos系统安装
```
yum update -y && yum install vim screen -y
```
# 二、安装ffmpeg

Ubuntu/Ddian系统安装ffmpeg
```
apt install ffmpeg
```
- Centos系统安装ffmpeg
```
yum install epel-release
rpm -v --import http://li.nux.ro/download/nux/RPM-GPG-KEY-nux.ro
rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
yum install ffmpeg ffmpeg-devel
```
- 检查是否安装成功
```
ffmpeg -version
```
# 三、下载推流脚本和上传直播视频

下载推流脚本：
```
wegt https://github.com/3981877/zhibo/releases/download/1.0/stream.sh
```
把想要做直播的视频上传到root目录下

注意：目前支持循环推流mp4格式的视频，视频文件的名字不能含有空格或其他特殊符号

1、新打开一个窗口（注意：这个点很关键）
```
screen -S stream
```
2、执行运行命令（注意：这里执行的是脚本的文件名，如果文件名更改，后面的stream.sh要改为对应的文件名）
```
bash stream.sh
```
3、新打开一个页面，查找ID
```
screen -ls
```
4、然后远程detach
```
screen -d id
```
