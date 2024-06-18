# git的基本配置

## 课程目标

1. 了解 git 与 github 的关系
2. 掌握 windows 下 git 的安装及配置
3. 掌握 powershell 、vscode 、githubDesktop 中 git 的使用
4. 掌握基础的 add 、commit 、push 、pull 操作

## 课程内容

###  git 与 github 的关系

- git 是一个分布式版本控制系统
- github 是一个基于 git 的代码托管平台

### windows 下 git 的安装及配置（使用scoop）

#### 安装 scoop

- 以管理员身份 打开 powershell，允许其执行脚本

```shell
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
```

- 执行以下命令，安装 scoop

```shell
iwr -useb get.scoop.sh | iex
```

- 安装完成后，执行以下命令，安装 git

```shell
scoop install git
```

#### 配置 git

- 配置用户名

```shell
git config --global user.name "yourname"
```

- 配置邮箱

```shell
git config --global user.email "youremail"
```

- 配置编辑器

```shell
git config --global core.editor "code --wait"
```

#### 配置 ssh

- 生成 ssh key

```shell
ssh-keygen -t rsa -b 4096 -C "youremail"
```

在用户目录下的 `.ssh` 文件夹中找到 `id_rsa.pub` 文件，将其内容添加到 github 上

- 在 github 上添加 ssh key

打开 github ，点击右上角头像，选择 `settings` ，点击 `SSH and GPG keys` ，点击 `New SSH key` ，将 `id_rsa.pub` 文件的内容粘贴到 `key` 中，点击 `Add SSH key`

### powershell 中 git 的使用

#### 创建仓库

- 在当前目录下创建一个新的 git 仓库

```shell
git init
```

- 克隆一个已有的 git 仓库

```shell
git clone github-repository-url
```

#### 添加文件

- 添加指定文件到暂存区

```shell
git add filename
```

- 添加所有文件到暂存区

```shell
git add .
```

#### 提交文件

- 提交暂存区的文件到仓库

```shell
git commit -m "message"
```

#### 推送文件

- 推送本地仓库的文件到远程仓库

```shell
git push
```

在此之前，需要设置远程仓库

```shell
git remote add origin github-repository-url
```
首次推送时，需要指定推送的分支

```shell
git push -u origin master
```
之后推送时，只需执行 `git push` 即可

#### 拉取文件

- 拉取远程仓库的文件到本地仓库

```shell
git pull
```

在此之前，需要设置远程仓库

```shell
git remote add origin github-repository-url
```

### vscode 中 git 的使用（重点）

#### 默认 git 集成

在 vscode 的左侧导航栏中有默认的 git 集成，在初始阶段中，可以使用默认的 git 集成，但是在后续的学习中，可以通过安装插件来提高效率

#### 初始化仓库

- 在 vscode 中初始化仓库

在 vscode 中打开一个文件夹，点击左侧导航栏中的 `源代码管理` ，点击 `初始化存储库` ，选择一个文件夹，点击 `选择存储库位置` ，点击 `选择存储库位置` ，完成初始化

#### 添加文件
    
- 在 vscode 中添加文件

在 vscode 中打开一个文件夹，点击左侧导航栏中的 `源代码管理` ，点击 `更改` ，点击 `+` ，完成添加，一般我们不做此操作，而是直接提交，vscode 会自动添加文件

#### 提交文件
    
- 在 vscode 中提交文件

在 vscode 中打开一个文件夹，点击左侧导航栏中的 `源代码管理` ，输入提交信息，点击 `√提交` 按钮 ，完成提交

#### 推送文件
        
- 在 vscode 中推送文件

在 vscode 中打开一个文件夹，点击左侧导航栏中的 `源代码管理` ，点击 `...` ，点击 `推送` ，完成推送

#### 拉取文件

- 在 vscode 中拉取文件

在 vscode 中打开一个文件夹，点击左侧导航栏中的 `源代码管理` ，点击 `...` ，点击 `拉取` ，完成拉取

### githubDesktop 中 git 的使用

#### 安装 githubDesktop

- 下载地址：https://desktop.github.com/

#### 初始化仓库

- 在 githubDesktop 中初始化仓库

点击 `File` ，点击 `Add Local Repository` ，选择一个文件夹，点击 `Add Repository` ，完成初始化

#### 添加文件

- 在 githubDesktop 中添加文件

点击 `Changes` ，点击 `Add` ，完成添加

#### 提交文件
    
- 在 githubDesktop 中提交文件

点击 `Summary` ，输入提交信息，点击 `Commit to master` ，完成提交

#### 推送文件
    
- 在 githubDesktop 中推送文件

点击 `Push origin` ，完成推送

#### 拉取文件
    
- 在 githubDesktop 中拉取文件

点击 `Pull origin` ，完成拉取




