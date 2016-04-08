1、先说一下什么是pip
pip 是“A tool for installing and managing Python packages.”，也就是说pip是python的软件安装工具
2、下面介绍怎么在linux下安装pip
下载pip到/usr/local/src
# cd /usr/local/src
# wget "https://pypi.python.org/packages/source/p/pip/pip-1.5.4.tar.gz#md5=834b2904f92d46aaa333267fb1c922bb" --no-check-certificate
如果提示：-bash: wget: command not found
那么安装wget，执行如下：
# yum -y install wget 

解夺安装pip
# tar -xzvf pip-1.5.4.tar.gz
# cd pip-1.5.4
# python setup.py install

如果安装报下面的错：
Traceback (most recent call last):
  File "setup.py", line 6, in <module>
    from setuptools import setup, find_packages
ImportError: No module named setuptools

那么就要先安装setuptools包
(1)下载setuptools包
# wget http://pypi.python.org/packages/source/s/setuptools/setuptools-2.0.tar.gz
(2)解压setuptools包
# tar zxvf setuptools-2.0.tar.gz
# cd setuptools-2.0
(3)编译setuptools
# python setup.py build
(4)开始执行setuptools安装
# python setup.py install

安装完成setuptools包后，在重新执行：
# cd /usr/local/src/pip-1.5.4
# python setup.py install
至此pip安装完成

3、linux下pip使用参数
# pip --help

Usage:   
  pip <command> [options]

Commands:
  install                     Install packages.
  uninstall                   Uninstall packages.
  freeze                      Output installed packages in requirements format.
  list                        List installed packages.
  show                        Show information about installed packages.
  search                      Search PyPI for packages.
  wheel                       Build wheels from your requirements.
  zip                         DEPRECATED. Zip individual packages.
  unzip                       DEPRECATED. Unzip individual packages.
  bundle                      DEPRECATED. Create pybundles.
  help                        Show help for commands.

General Options:
  -h, --help                  Show help.
  -v, --verbose               Give more output. Option is additive, and can be used up to 3 times.
  -V, --version               Show version and exit.
  -q, --quiet                 Give less output.
  --log-file <path>           Path to a verbose non-appending log, that only logs failures. This log is active by default at /root/.pip/pip.log.
  --log <path>                Path to a verbose appending log. This log is inactive by default.
  --proxy <proxy>             Specify a proxy in the form [user:passwd@]proxy.server:port.
  --timeout <sec>             Set the socket timeout (default 15 seconds).
  --exists-action <action>    Default action when a path already exists: (s)witch, (i)gnore, (w)ipe, (b)ackup.
  --cert <path>               Path to alternate CA bundle.
