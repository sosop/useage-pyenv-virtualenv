## pyenv 安装与使用

#### 先安装git

```shell
sudo apt-get install git # debian
sudo yum install git # centos
brew install git # macos
```

#### 克隆pyenv仓库

```shell
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

#### 设置bash环境变量PYENV_ROOT/pyenv init

```shell
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n eval "$(pyenv init -)"\nfi' >> ~/.bashrc
source ~/.bashrc # or exec $SHELL
```

#### 升级

```shell
cd ~/.pyenv && git pull
```

#### 基本使用

```shell
pyenv activate    	# 激活 virtual environment，需要安装pyenv-virtualenv
pyenv commands    	# 列出所有可用命令
pyenv deactivate   	# 停用 virtual environment
pyenv global      	# 设置 or 显示 the global Python version(s)
pyenv help        	# 展示具体命令的帮助
pyenv init        	# Configure the shell environment for pyenv
pyenv install     	# Install a Python version using python-build
pyenv local       	# Set or show the local application-specific Python version(s)
pyenv rehash      	# Rehash pyenv shims (run this after installing executables)
pyenv root        	# Display the root directory where versions and shims are kept
pyenv shell       	# Set or show the shell-specific Python version
pyenv shims       	# List existing pyenv shims
pyenv uninstall   	# Uninstall a specific Python version
pyenv --version   	# Display the version of pyenv
pyenv version     	# Show the current Python version(s) and its origin
pyenv versions    	# List all Python versions available to pyenv
pyenv virtualenv   	# Create a Python virtualenv using the pyenv-virtualenv plugin
pyenv virtualenv-delete   	# Uninstall a specific Python virtualenv
pyenv virtualenv-init   	# Configure the shell environment for pyenv-virtualenv
pyenv virtualenv-prefix   	# Display real_prefix for a Python virtualenv version
pyenv virtualenvs   		# List all Python virtualenvs found in `$PYENV_ROOT/versions/*'.
pyenv whence      	# List all Python versions that contain the given executable
pyenv which       	# Display the full path to an executable

# See `pyenv help <command>' for information on a specific command
```

***默认安装了pip***



## pyenv-virtualenv虚拟环境管理工具

#### 克隆

```shell
git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
```

#### 配置环境变量

```shell
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
exec $SHELL # or source ~/.bashrc
```

#### 基本使用

```shell
pyenv virtualenvs						# 查看工作环境
pyenv virtualenv 3.8.1 project_name 	# 激活项目对应的环境
pip install flask==1.1 					# 当前环境安装flask指定版本
pyenv deactivate 						# 退出当前工作环境
pyenv virtualenv-delete project_name	# 删除虚拟环境
```

