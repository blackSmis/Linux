# linux操作

常用命令
---

编号 | 命令 | 说明
---|---|---
1 | ls | 查看当前目录下的文件
2 | cd |  切换目录
3 | pwd |  查看当前目录
4 | touch |    创建文件
5 | mkdir |   新建目录
6 | rm | 删除文件
7 |clear |   清屏

查询指令
---
```
command --help
man command //空格 enter b f q
```
ls常用选项
---
以 . 开头的为隐藏文件
参数 | 说明
---|---
-a | 查看所有文件
-l | 查看文件详细信息
-h | 人性化显示文件大小

```
ls -lha //参数可连接使用
```

ls通配符
---
参数 | 说明
---|---
* | 表示任意个数字符
？ | 表示一个字符
[] | 表示可匹配字符组中的任意一个字符
[abc] | 表示可匹配a、b、c中任意一个字符
[a-z] | 表示可匹配a-z中的任意一个字符
```
ls *.txt    //匹配以.txt结尾的文件    
ls ?1.txt   //匹配以任意一个字符开头，以1.txt结尾的文件
ls [123].txt    //匹配1.txt、2.txt、3.txt
ls [a-z].txt    //匹配a.txt、b.txt...z.txt
```
cd命令
---
```
cd/cd ~  //切换到当前用户目录
cd ..   //切换到上级目录
cd -    //最近的两个目录之间切换
```
mkdir命令
---
```
mkdir a //创建一个a的文件夹
mkdir -p a/a/a/ //递归创建文件夹
```
rm命令
---
```
rm -f abc //无提示删除
rm -r abc //递归删除目录
rm -rf * //可使用通配符
```
tree命令
---
```
<!--以树状图显示目录结构-->
tree //以树状图显示当前目录结构
tree -p //以树状图显示当前目录结构,只显示目录
```
cp命令
---
```
<!--复制文件-->
cp a b //将a文件复制为b文件
cp -i a . //同名时提示是否覆盖
cp -r a b //可复制目录
```
查看文件内容
---
```
cat a -b //全部显示,显示行号，换行不显示
cat a -n //全部显示，显示行号，换行也显示
more a //分屏显示 空格 enter b f q
grep -nvi he a.txt //在a.txt中查找he的位置 -n显示行号 -v取反  -i忽略大小写
grep ^a a.txt //在a.txt中查找以a开头的行
grep a$ a.txt //在a.txt中查找以a结尾的行
ifconfig | grep inet //查看本机IP地址
```
echo 和重定向
---
```
echo hello > a  //为a中添加内容，会覆盖
echo hello >> a  //为a中追加内容
tree >> a
```
ssh 和 scp
---
```
ssh -p 22 ubuntu@192.168.0.8    //将本地与linux连接
scp -P 22 -r ubuntu@192.168.0.8:Desktop/a . //将linux文件复制到本地 -r表示可复制目录
scp -P 22 -r a ubuntu@192.168.0.8:Desktop/a //本地文件复制到linux
```
chmod命令
---
```
chmod +/-rwx 文件名/目录名  //修改文件或目录权限 +增/-减 rwx 读写执行
```
which命令
---
```
which ls //查询命令所在位置
```
进程命令
---
```
ps sux //查看进程 a终端所有 u详细 x非终端
kill [-9] 进程代号 //关闭指定进程 -9强行关闭
```
其他命令
---
```
<!--查询文件-->
find [目录] -name "*.py" //在指定目录下搜索以.py结尾的文件
ln -s 源文件位置 链接文件 //使用绝对路径避免文件移动 创建软链接
<!--压缩/解压文件-->
tar -cvf 打包文件.tar 被打包文件的路径  //打包文件
tar -xvf 打包文件.tar //解包文件

tar -zcvf 压缩文件.tar.gz 被压缩文件的路径  //压缩文件
tar -zxvf 压缩文件.tar.gz -C 压缩到指定目录 //解压文件 目录必须存在

tar -jcvf 压缩文件.tar.bz2 被压缩文件的路径  //压缩文件
tar -jxvf 压缩文件.tar.bz2 -C 压缩到指定目录 //解压文件 目录必须存在
<!--安装卸载更新软件-->
sudo apt install 软件包 //安装软件
sudo apt remove 软件名 //卸载软件
sudo apt upgrade //更新软件

```
