<h1 align="center">Apple ID unlocker backend program[Single account local deployment, not docker]</h1>

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

# [English](https://github.com/yuanweize/appleid_unlocker/blob/backend/README_EN.md) | [Chinese](https://github.com/yuanweize/appleid_unlocker/blob/backend/README.md)

<h3 align="center">Please read this document carefully and the wiki document we will launch in the future before using it. </h3>

<h3 align="center">This project is still being updated. </h3>

# Basic introduction

"Manage your Apple ID in a new way" - This is an automated Apple ID detection & unlocking program based on password problems.

Single back-end management of a single account, and provide a display account page to view the main branch;

The back-end regularly detects whether the account is locked. If it is locked or two-step verification is turned on, it will automatically unlock, modify the password and return the password to the API.

### Caution:

1. main**back-end program**, deploy through systemctl and obtain task parameters from API [single task];

2. Program**requires Chrome webdriver**, ~~Docker version is recommended [selenium/standalone-chrome] (https://hub.docker.com/r/selen Ium/standalone-chrome), please find your own way to use it.~~


Download address format[106.0.5249.61]:**https://chromedriver.storage.googleapis.com/index.html?path=106.0.5249.61/**
chromedriver install command [note version]:
```
wget https://chromedriver.storage.googleapis.com/106.0.5249.61/chromedriver_linux64.zip
unzip chromedriver_linux64.zip
mv chromedriver /usr/bin/
#Grant enforcement authority
chmod +x /usr/bin/chromedriver
```
3. tg_bot's job command adds tg notification
# Issue Feedback & Communication

The level and ability of developers are limited, and there may be many bugs in the program. You are welcome to ask Issue or Pull Request, and you are also welcome to join the project!

Telegram group: [@appleunblocker] (https://t.me/appleunblocker)

# Usage

**Please make sure that Webdriver is deployed before use**

### One-click deployment unblocker_backend:

`wget https://raw.githubusercontent.com/yuanweize/appleid_unlocker/backend/backend/install_backend.s H && bash install_backend.sh`

# File Description

- `backend\main.py` Back-end unlocker \
Description: Account recryption and unlocking through Webdriver and submit a new password to the API. **This program relies on the API** \
Startup parameters: `-api_url <API address> -api_key <API key>
Deploy **back-end administrator**, the script will automatically get the task [single task only] from the API site and deploy the container. The default synchronization time is 10 minutes (manual synchronization can restart the service) \
# TODO List

- [x] Automatic identification verification code
- [x] Detect that the account is locked
- [x] Detect two-step verification
- [ ] Check that the password is correct
- [ ] Delete the device
- [x] Modify the password
- [x] Escalate the password
- [x] Telegram Bot Notification