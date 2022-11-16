<h1 align="center">Apple ID 解锁后端程序[单账号本地部署,非docker]🔒</h1>
<p align="center">
    <a href="https://github.com/pplulee/appleid_auto/issues" style="text-decoration:none">
        <img src="https://img.shields.io/github/issues/pplulee/appleid_auto.svg" alt="GitHub issues"/>
    </a>
    <a href="https://github.com/pplulee/appleid_auto/stargazers" style="text-decoration:none" >
        <img src="https://img.shields.io/github/stars/pplulee/appleid_auto.svg" alt="GitHub stars"/>
    </a>
    <a href="https://github.com/pplulee/appleid_auto/network" style="text-decoration:none" >
        <img src="https://img.shields.io/github/forks/pplulee/appleid_auto.svg" alt="GitHub forks"/>
    </a>
    <a href="https://github.com/pplulee/apple_auto/blob/main/LICENSE" style="text-decoration:none" >
        <img src="https://img.shields.io/github/license/pplulee/appleid_auto" alt="GitHub license"/>
    </a>
</p>

# [English](https://github.com/yuanweize/appleid_unlocker/blob/backend/README_EN.md) | [中文](https://github.com/yuanweize/appleid_unlocker/blob/backend/README.md)

<h3 align="center">请仔细阅读本文档以及未来我们会推出的 Wiki 文档，再使用。</h3>  
<h3 align="center">本项目仍在更新当中。</h3>

# 基本简介

“以全新方式管理你的 Apple ID” —— 这是一款基于密保问题的自动化 Apple ID 检测&解锁程序。

单后端管理单个账号,并提供展示账号页面,查看main分支；

后端定时检测账号是否被锁定，若被锁定或开启二步验证则自动解锁，修改密码并向API回报密码。

### 注意事项：


1. main**后端程序**，通过systemctl部署并从API获取任务参数[单任务]；
2. 程序**需要使用Chrome webdriver**，~~推荐使用Docker版 [selenium/standalone-chrome](https://hub.docker.com/r/selenium/standalone-chrome)，使用方法请自行寻找。~~
下载地址格式[106.0.5249.61]:**https://chromedriver.storage.googleapis.com/index.html?path=106.0.5249.61/**
```
wget https://chromedriver.storage.googleapis.com/106.0.5249.61/chromedriver_linux64.zip
unzip chromedriver_linux64.zip
mv chromedriver /usr/bin/
给予执行权限
chmod +x /usr/bin/chromedriver
```

# 问题反馈&交流
开发者水平和能力有限，程序可能存在诸多bug，欢迎提出 Issue 或 Pull Request ，也欢迎各位大佬加入项目！
Telegram群：[@appleunblocker](https://t.me/appleunblocker)

# 使用方法
**使用前请确保已部署好 Webdriver**

### 一键部署unblocker_backend：
`wget https://raw.githubusercontent.com/yuanweize/appleid_unlocker/backend/backend/install_backend.sh && bash install_backend.sh`

# 文件说明
- `backend\main.py` 后端解锁程序 \
说明：通过Webdriver实现账号改密解锁，并向API提交新密码。**该程序依赖API运行** \
启动参数：`-api_url <API地址> -api_key <API key> 
部署**后端管理程序**，该脚本会自动从API站点获取任务[仅单任务]并部署容器，默认同步时间为10分钟（手动同步可重启服务） \

# TODO List
- [x] 自动识别验证码
- [x] 检测账号被锁
- [x] 检测二步验证
- [ ] 检查密码正确
- [ ] 删除设备
- [x] 修改密码
- [x] 上报密码
- [x] Telegram Bot通知
