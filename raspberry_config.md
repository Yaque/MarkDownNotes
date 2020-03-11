    username:pi
    password:raspberry
    sudo raspi-config
    intraface option
    ssh
    enable
    python
    python3
    pip
    pip3
    
    sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
    sudo cp /etc/apt/sources.list.d/raspi.list /etc/apt/sources.list.d/raspi.list.bak
    
[清华raspberry的软件源与系统源](https://mirror.tuna.tsinghua.edu.cn/help/raspbian/)

    # 编辑 `/etc/apt/sources.list` 文件，删除原文件所有内容，用以下内容取代：
    deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib
    deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib
    
    # 编辑 `/etc/apt/sources.list.d/raspi.list` 文件，删除原文件所有内容，用以下内容取代：
    deb http://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ buster main ui

    更新源中包数据
    sudo apt-get update
    更新包
    sudo apt-get upgrade
    更新包的依赖
    sudo apt-get dist-upgrade
    更新固件，不建议使用
    sudo rpi-update

    sudo apt install python3-pip
    
    sudo pip3 install -i 清华源 django
    https://pypi.tuna.tsinghua.edu.cn/simple
    
    sudo apt-get install  nginx
    sudo apt-get install git
    
    git clone project folder
    
    into project root dir
    
    don't remenber change the setting.py file
    
    # 关闭调试模式
    DEBUG = False
    
    # 允许的服务器
    ALLOWED_HOSTS = ['*']
    
    # 静态文件收集目录
    STATIC_ROOT = os.path.join(BASE_DIR, 'collected_static')
    
    python3 manage.py collectstatic
    python3 manage.py migrate
    
    sudo service nginx static
这样不会安装出错。