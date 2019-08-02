### 安裝

- brew install `<software name>` 安装非圖形软件
- brew cask 并不喜欢 brew cask 的安装方式，更倾向于到 App Store 或官方下载 OS X 图形界面程序。主要因为名字不好记忆、偶尔需要手动更新
  - brew cask -help 查看帮助
  - brew cask install <software name> 安装软件
  - brew cask uninstall <software name> 卸载软件
  - brew cask search <software name> 搜索软件
  - brew cask info <software name> 查看软件相关信息
  - brew cask list 列出通过 Homebrew-Cask 安装的包

### 清理旧版本

新版本安装了，旧版本就不需要了。我会用 brew cleanup 清理旧版本和缓存文件。Homebrew 只会清除比当前安装的包更老的版本，所以不用担心有些包没更新但被删了。

`brew cleanup` # 清理所有包的旧版本

`brew cleanup $FORMULA` # 清理指定包的旧版本

`brew cleanup -n` # 查看可清理的旧版本包，不执行实际操作

现在该更新的都更新了，旧版本也被清理。

对于 Homebrew 来说，如果没有卸载掉软件包的所有版本，那么 Homebrew 会继续尝试安装这个软件包的最新版本。要想彻底卸载某个软件包，需要执行命令：

`brew uninstall formula_name --force`

### 锁定不想更新的包

如果经常更新的话，brew update 一次更新所有的包是非常方便的。但我们有时候会担心自动升级把一些不希望更新的包更新了。数据库就属于这一类，尤其是 PostgreSQL 跨 minor 版本升级都要迁移数据库的。我们更希望找个时间单独处理它。这时可用 brew pin 去锁定这个包，然后 brew update 就会略过它了。

    brew pin $FORMULA      # 锁定某个包
    brew unpin $FORMULA    # 取消锁定

### 服务管理

brew services 用于方便的管理 brew 安装的软件软件，类似于 Linux 下的 service 命令。

    brew services command:
    Integrates Homebrew formulae with macOS' launchctl manager.
    
    [sudo] brew services list:
    List all running services for the current user (or root).
    
    [sudo] brew services run (formula|--all):
    Run the service formula without registering to launch at login (or boot).
    
    [sudo] brew services start (formula|--all):
    Start the service formula immediately and register it to launch at login (or boot).
    
    [sudo] brew services stop (formula|--all):
    Stop the service formula immediately and unregister it from launching at login (or boot).
    
    [sudo] brew services restart (formula|--all):
    Stop (if necessary) and start the service formula immediately and register it to launch at login (or boot).
    
    [sudo] brew services cleanup:
    Remove all unused services.
    
    If sudo is passed, operate on /Library/LaunchDaemons (started at boot).
    Otherwise, operate on ~/Library/LaunchAgents (started at login).

### 查看配置信息

brew config 用于查看 brew 所在环境及相关的配置情况

### 诊断问题

brew doctor 诊断当前 brew 存在哪些问题，并给出解决方案

### 仓库管理

    brew tap 已安装的仓库列表
    
    brew tap [--full] user/repo [URL] 添加仓库
    
    brew untap tap 移除仓库

### 长时间卡

```bash
➜  ~ brew install composer
Updating Homebrew... # 如果碰到长时间卡在这里，参考以下 2 种处理方法
```

- 临时的、一次性的方法：按住 control + c 取消本次更新操作,按住 control + c 之后命令行会显示 ^C，就代表已经取消了 Updating Homebrew 操作大概不到 1 秒钟之后就会去执行我们真正需要的安装操作了

  ```bash
  ➜  ~ brew install composer
  Updating Homebrew...
  ^C==> Satisfying dependencies
  ==> Downloading https://getcomposer.org/download/1.7.2/composer.phar
  ···
  ```

- 操作 homebrew 源

  - 替换 / 还原brew.git:

  ```bash
      cd "$(brew --repo)"
      git remote set-url origin https://mirrors.aliyun.com/homebrew/brew.git

      // https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git
      // https://mirrors.ustc.edu.cn/brew.git

      # 还原为官方提供的 brew.git 仓库地址
      cd "$(brew --repo)"
      git remote set-url origin https://github.com/Homebrew/brew.git
  ```

  - 替换 / 还原homebrew-core.git:

  ```bash
      cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
      git remote set-url origin https://mirrors.aliyun.com/homebrew/homebrew-core.git

      // https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git
      // https://mirrors.ustc.edu.cn/homebrew-core.git

      # 还原为官方提供的 homebrew-core.git 仓库地址
      cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
      git remote set-url origin https://github.com/Homebrew/homebrew-core.git
  ```

  - 可选 替换 / 还原 homebrew-bottles 访问地址

  ```bash
      #这个步骤跟你的 macOS 系统使用的 shell 版本有关系，所以，先来查看当前使用的 shell 版本

      echo $SHELL

      # 如果你的输出结果是 /bin/zsh，参考下方的 zsh 终端操作方式
      # 如果你的输出结果是 /bin/bash，参考下方的 bash 终端操作方式

      ## zsh终端操作方式
      # 替换成阿里巴巴的 homebrew-bottles 访问地址:
      echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.zshrc
      source ~/.zshrc

      #=======================================================

      # 还原为官方提供的 homebrew-bottles 访问地址
      vi ~/.zshrc
      # 然后，删除 HOMEBREW_BOTTLE_DOMAIN 这一行配置
      source ~/.zshrc

      ## bash 终端操作方式
      # 替换 homebrew-bottles 访问 URL:
      echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.aliyun.com/homebrew/homebrew-bottles' >> ~/.bash_profile
      source ~/.bash_profile
  ```

- 禁用掉每次安装前的更新(可选)

  ```bash
    # ~/.zshrc
    export HOMEBREW_NO_AUTO_UPDATE=true
  ```

    需要更新包了，可以执行：

  ```bash
    brew update && brew upgrade && brew cleanup ; say mission complete
    brew update && brew upgrade brew-cask && brew cleanup ; say mission complete
  ```

### homebrew 可视化管理工具

如果你不想去记忆那么多命令，也可以使用 `Cakebrew` （[官网](https://www.cakebrew.com/)）可视化管理

### homebrew services 可视化管理

[LaunchRocket](https://github.com/jimbojsb/launchrocket) 是非常友好的图形界面，使用起来简单快捷。比如你使用 Homebrew 安装的 Mysql、Redis、MongoDB，是让它自启动呢，还是手动启动，传统方式需要使用命令行的命令，而使用 `LaunchRocket` 则可以在图形界面中进行管理了！

安装方法：

    brew tap jimbojsb/launchrocket
    brew cask install launchrocket
