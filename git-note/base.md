# 使用 git 管理前的一些准备

### 配置本地 git 账号

```
git config user.name "Jiang Xin"
git config user.email "gotgithub@gmail.com"
```

### 本地生成 ssh-key

1. 直接生成

```
cd
ssh-keygen
```

其中第一步的`cd`是进入默认根目录, 然后一路按`回车`选择默认项即可.

```
cd ./.ssh
ll
```

2. 添加参数

```
-b  采用长度1024bit的密钥对,b=bits,最长4096，不过没啥必要
-t  加密方式,t=type
-f  生成文件名,f=output_keyfiles
-C  备注内容,C=comment
```

例如

```
ssh-keygen -t rsa -b 1024 -f yourkeyname -C "备注"
```

进入默认根目录, 然后进入`.ssh`文件夹即可看到生成的两个密钥文件:`id_rsa`(私钥), `id_rsa.pub`(公钥).

```
// 打印公钥内容
cat id_rsa.pub

// 复制公钥文件内容到剪贴板
clip < id_rsa.pub
```

登录 github 账号, 在`设置-ssh-key`中添加你的公钥

最后验证是否生效

```
ssh -T git@github.com
```

### 一些配置

1. 禁用 windows 的`crlf`换行符

因为在线上仓库使用的`linus`系统的换行符是`lf`,windows 用的是`crlf`.在拉取项目到本地会默认转化换行符.

```
git config --global core.autocrlf false
```
