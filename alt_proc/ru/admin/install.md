---
layout: page
title: alt_proc
---
# Инсталляция

## OS
```
Ubuntu 20.04 LTS minimized
sudo apt install net-tools postgresql
```
## Python 
```
3.7-3.9
https://docs.conda.io/en/latest/miniconda.html
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod u+x Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
conda install pyaml psutil psycopg2 uvicorn
pip install fastapi
```
## Layout
```
mkdir alt_proc
mkdir alt_proc/projects
mkdir alt_proc/wd/launcher
mkdir alt_proc/wd/ui
```
## Get sources
```
cd alt_proc/projects
git clone git@github.com:altyntsev/alt_proc_api.git
git clone git@github.com:altyntsev/alt_proc_libs.git
git clone git@github.com:altyntsev/alt_proc_launcher.git
git clone git@github.com:altyntsev/alt_proc_ui.git
git clone git@github.com:altyntsev/alt_proc_proc_tpl.git
```
## Database
```
sudo -u postgres psql
create user alt_proc with encrypted password 'alt_proc';
create database alt_proc;
alter database alt_proc owner to alt_proc;
psql -U alt_proc -d alt_proc -a -f \
    alt_proc/projects/alt_proc_api/main/install/db.sql 
```
## Cfg
/alt_proc/projects/_cfg/alt_proc.cfg
db:
    host: 127.0.0.1
    db: alt_proc
    user: alt_proc
    pwd: alt_proc
ui_users:
    - login: alt_proc
      pwd: alt_proc
            


