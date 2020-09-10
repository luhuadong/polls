# polls
polls - a web demo based on Django



## 环境搭建

### 安装 Python 虚拟环境

以 Ubuntu 为例，安装虚拟环境

```shell
sudo apt-get install python3-venv
```

创建虚拟环境

```shell
python3 -m venv venv
```

激活虚拟环境

```shell
source venv/bin/activate
```

关闭虚拟环境

```shell
deactivate
```



### 安装 Django

进入虚拟环境，安装 Django。

（1）在线安装 Django，指定版本安装，目前 2.2 LTS 的最新版为 2.2.16

```shell
pip install Django==2.2.16
```

默认会安装：`Django==2.2.16` 和 `pytz==2020.1`

（2）检测当前是否安装 Django 及版本

```shell
python -m django --version

2.2.16
```

或者使用 `pip freeze` 命令检查

```shell
pip freeze | grep Django

Django==2.2.16
```

此外，我们也可以先下载安装包，再指定安装包安装：

```shell
pip download django=2.2.16 -d ./
pip install Django-2.2.16-py2.py3-none-any.whl
```



### 创建项目

```shell
django-admin startproject mysite
```



### 运行项目

```shell
cd mysite/
python manage.py runserver
```



### 创建应用

```shell
python manage.py startapp polls
```



## 数据库

### 创建数据库

```sql
CREATE DATABASE IF NOT EXISTS polls DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
```

创建后，通过 `use polls;` 切换数据库。



### 安装 mysqlclient

在 Ubuntu 中安装依赖

```shell
sudo apt-get install libmysqlclient-dev
```

再安装 mysqlclient

```shell
pip3 install mysqlclient
```

执行迁移

```shell
python manage.py migrate
```



### 安装 pymysql

```shell
pip install PyMySQL
```

如果使用 pymysql，则需要在 `__init__.py` 文件中添加：

```shell
import pymysql

pymysql.install_as_MySQLdb()
```



提示：mysqlclient 的性能要好于 pymsql

