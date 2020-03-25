思路：<br>
1、申请谷歌云<br>
2、为第六步要用的SSH工具准备密匙<br>
3、在谷歌云创建虚拟机实例，也就是服务器<br>
4、准备一个域名，购买域名或者用免费域名都可以<br>
5、把域名解析到谷歌云服务器地址<br>
6、利用SSH工具连接谷歌云服务器，在服务器上部署Trojan服务
# 一、申请谷歌云并创建防火墙规则
## 1、申请谷歌云
* 打开[谷歌云官网](https://cloud.google.com/)，点免费开始试用，选择一个国家，我这里以日文为例，这里选择哪个国家都可以。如图
![谷歌云申请300$](https://www.louimg.com/u/20200325/17012694.png "谷歌云申请300$")
![谷歌云申请300$](https://www.louimg.com/u/20200325/17012963.png "谷歌云申请300$")
* 接下来填写信息，信息完成后，点击开始免费试用，具体见下图：<br>
  * 账号类型选择个人；<br>
  * 不管选择哪个国家，这里的地址信息一定写真实的地址，我是用谷歌搜了一个大阪的具体地方，网上有很多地址生成器也可以用。姓名随便写；<br>
  * 信用卡信息全部写自己的真实信息，持卡人姓名写自己真实姓名；<br>
![谷歌云申请300$](https://www.louimg.com/u/20200325/17112558.png "谷歌云申请300$")
![谷歌云申请300$](https://www.louimg.com/u/20200325/17112824.png "谷歌云申请300$")
* 申请成功后，直接进入到控制台页面。Google会从信用卡扣除1美元用于验证, 验证完成后会退还到账户，我因为选的国家是日本，所以按等额的日元的扣的。具体如下图。<br>
![谷歌云申请300$](https://www.louimg.com/u/20200325/17334963.png "谷歌云申请300$")
![谷歌云申请300$](https://www.louimg.com/u/20200325/1733525.jpg "谷歌云申请300$")
## 2、创建防火墙规则
进入谷歌云后台，按照下图路劲找到防火墙规则，点击创建防火墙规则，需要填写的地方已用红圈圈出，如下图。<br>
* 注意来源IP地址范围是0.0.0.0/0
* 目标选为网络中所有实例
![创建防火墙规则](https://www.louimg.com/u/20200325/18255456.png "创建防火墙规则")
![创建防火墙规则](https://www.louimg.com/u/20200325/18255798.png "创建防火墙规则")


# 二、准备SSH工具密匙


# 三、准备域名和解析
## 域名购买
这里以购买域名为例，免费的域名网上很多，比如可到Freenom申请。不过还是建议购买一个域名，因为综合来说更稳定，况且现在的域名价格也不是很贵。[免费跟付费的域名有什么区别，请点击查看](https://blog.csdn.net/liangtaox8/article/details/96839227)。我是在大名鼎鼎的域名提供商godaddy([官网](https://www.godaddy.com/))上购买的。当初是准备建设一个自己的博客而买的。当然越常见的域名后缀价格越高，比如.com、.net、.cn、.org等这些就属于常见的域名。我的购买账单如图：<br>
![godaddy账单](https://www.louimg.com/u/20200322/19103367.png "godaddy账单")
* 大致讲一下购买步骤：打开官网，输入你想要的域名，比如我输入了sxcool1024，点击搜索，就会列出所有域名，根据自己需求选择，加入购物车，购买。具体如下图<br>
![godaddy购买](https://www.louimg.com/u/20200325/15270758.png "godaddy购买")
![godaddy购买](https://www.louimg.com/u/20200325/15271181.png "godaddy购买")
![godaddy购买](https://www.louimg.com/u/20200325/15394149.png "godaddy购买")
![godaddy购买](https://www.louimg.com/u/20200325/15394328.png "godaddy购买")
## 域名解析
* 准备DNS服务器，这里推荐用DNSPOD([官网](https://www.dnspod.cn))，这是一个提供免费域名解析的网站，自行注册，注册完成后，进入控制台，找到DNS管理->我的域名，添加域名。如下图
![域名解析](https://www.louimg.com/u/20200325/15515655.png "域名解析")
* 点击添加的域名，如下图
![域名解析](https://www.louimg.com/u/20200325/15515655.png "域名解析")
