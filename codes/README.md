# 使用说明：
为了保护仓库PHP源码，已经对源码进行不可逆的加密处理，使用方法如下：

推荐使用肥羊PHP集成解密扩展Docker镜像：
# 一键运行：
# amd64架构：

docker run -d --restart unless-stopped --privileged=true -p 5678:80 --name php-env youshandefeiyang/php-env
# arm64架构：

docker run -d --restart unless-stopped --privileged=true -p 5678:80 --name php-env youshandefeiyang/php-env:arm64
# 然后执行：
docker cp /你的本地PHP文件地址/xxx.php php-env:/var/www/html/
# 访问地址：
http://你的IP:5678/xxx.php?id=xxx&xx=xxx...
# gudou.php使用方法：
1.需要在ROOT的安卓手机/安卓模拟器安装抓包工具（已在software目录提供），本套谷豆源码只适合安卓版本
2.安装9004版谷豆（已在software目录提供）
3.注册并登录自己的手机号码，开启抓包后筛选关键词aut002，然后puser是你的手机号，你需要记录ptoken和pserialnumber以及cid
4.最后在IPTV播放器访问∶

http://你的IP:5678/gudou.php?phone=你的手机号&ptoken=你的ptoken&pserialnumber=你的pserialnumber&cid=你的cid&id=谷豆频道对应id


# php部署
# 1、docker扩容：磁盘管理新增，格式ext4，挂载点新增，uuid选新增盘，挂载给docker,下方挂载点打√启用,重启系统
# 2、ssh（finalshell）工具连接openwrt
# 3、pwd进root文件夹
# 4、下方root内新建test文件夹
# 5、cd test
# 6、上传xxxx.php进去
# 7、docker run -d --restart unless-stopped --privileged=true -p 5658:80 --name php-env youshandefeiyang/php-env:arm64
# 8、docker cp /root/test/xxxx.php php-env:/var/www/html/
# 9、播放地址：http://软路由地址:5678/xxxx.php
#    http://软路由地址:5678/xxx.php?id=xxx&xx=xxx...

列出docker容器内文件
docker exec -it php-env ls  
删除xxx.php
docker exec -it php-env rm xxx.php  
docker exec php-env rm /var/www/html/xxx.php
