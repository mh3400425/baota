安装命令：
yum install -y wget && git clone -b master https://github.com/mh3400425/baota && bash install.sh

yum install -y wget && wget -N --no-check-certificate https://github.com/mh3400425/baota.git && bash install.sh

去除官网登陆绑定
这是破解的核心一旦绑定破坏就达不到目的了
这里提供了两次方法直接在终端执行就行了

第一种方法是删除验证文件
mv /www/server/panel/data/bind.pl ./

第二种方法我们把登录文件重命名此文件为bind.pl.bak
mv /www/server/panel/data/bind.pl /www/server/panel/data/bind.pl.bak

破解插件
我们进到 /www/server/panel/data/ 目录
编辑plugin.json文件
点击替换按钮，搜索
"endtime": -1
替换为
"endtime": 999999999999
点击 All进行全部替换
![image](https://user-images.githubusercontent.com/108580514/177044217-0500df68-ad6c-4184-aff4-66f7304832f9.png)
修改好之后我们点保存 
然后专业/企业版软件都可以使用了

改图标
图标还是在那个文件
搜索
is_user_status
把 “ltd”: -1 和 “pro”: -1 这两个 -1 改为 0
ltd是企业版 pro是专业版
-1代表没授权，0代表专业版永久授权
然后点击保存按钮即可

取消自动修复
因为宝塔会自动修复
后面我要用到宝塔APP 所以我采用的是方法二
解决方法1
在面板设置里打开离线模式。
解决方法2
用Linux chattr命令改变文件属性。
打开宝塔终端或者xshell，输入下面代码：
chattr +i /www/server/panel/data/plugin.json
 解除则输入
chattr -i /www/server/panel/data/plugin.json
