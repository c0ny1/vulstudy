# vulstudy

vulstudy是专门收集当下流行的漏洞学习平台，并将其制作成docker镜像，方便大家快速搭建环境，节省搭建时间，专注于的漏洞学习上。目前`vulstudy`包含以下漏洞学习平台：

|序号|漏洞平台|包含漏洞|作者|语言|
|:---:|:---:|:----:|:---:|:---:|
|1|[DVWA](http://www.dvwa.co.uk)|暴力破解，XSS，CSRF，SQL注入，命令执行|未知|php|
|2|[bwapp](https://sourceforge.net/projects/bwapp/)|综合|未知|php|
|3|[sqli-labs](https://github.com/Audi-1/sqli-labs)|SQL注入|[Audi](https://github.com/Audi-1)|php|
|4|[mutillidae](http://sourceforge.net/projects/mutillidae)|综合|OWASP|php|
|5|[BodgeIt](https://github.com/psiinon/bodgeit)|综合|[psiinon](https://github.com/psiinon/bodgeit)|java|
|6|[WackoPicko](https://github.com/adamdoupe/WackoPicko)|综合|[adamdoupe](https://github.com/adamdoupe)|php|
|7|[WebGoat](https://github.com/WebGoat/WebGoat)|综合|OWASP|java|
|8|[Hackademic](https://github.com/Hackademic/hackademic)|综合|[northdpole](https://github.com/northdpole)|php|
|9|[XSSed](https://github.com/aj00200/xssed)|XSS|AJ00200|php|
|10|[DSVW](https://github.com/stamparm/DSVW)|综合|Miroslav Stampar|python|
|11|[vulnerable-node](https://github.com/cr0hn/vulnerable-node)|综合|[cr0hn](https://github.com/cr0hn)|NodeJS|
|12|[MCIR](https://github.com/SpiderLabs/MCIR)|综合|[Spider Labs](https://github.com/SpiderLabs)|php|

## 0x01 安装

```
# 安装docker
apt-get install docker.io
# 安装docker-compose
pip install docker-compose
# 下载vulstudy项目 
git clone https://github.com/c0ny1/vulstudy.git
```

## 0x02 使用
使用主要分两种：单独运行一个漏洞平台，同时运行多个漏洞平台。

#### 1.单独运行一个漏洞平台

cd到要运行的漏洞平台下运行以下命令

```
cd vulstudy/dvwa
docer-compose up -d #启动
docker-compose stop #停止
```

#### 2.同时运行所有漏洞平台

在项目根目录下运行以下命令

```
cd vulstudy
docker-compose up -d
```
![主界面](doc/vulstudy.jpg)

## 0x3 FAQ
**1.第一次bWAPP容器访问主页会报错如下**

```
Connection failed: Unknown database 'bWAPP'
```

**解决：** 第一次创建应事先访问/install.php来创建数据库！

## 0x4 声明
该项目只是收集了当下比较流行的漏洞学习平台，若有侵权，请联系我！同时欢迎大家提交更多有意思的漏洞学习平台，让我们一起把它们放到docker上，方便更多人的工作和学习！