# -

## iterm2

- 将 iTem2 设置为默认终端：（菜单栏）iTerm2 -> Make iTerm2 Default Term

- hotkey Hotkey 下的 Show/hide iTerm2 with a system-wide hotkey,这样可以通过全局热键来打开或关闭 iTerm2 窗口，非常方便

### 常用快捷键

- ⌘+T 打开一个新的标签页
- ⌘+; 弹出自动补齐窗口
- ⌘+Shift+; 弹出历史命令记录窗口
- ⌘+Shift+H 弹出历史粘贴记录窗口
- ⌘+←、⌘+→、 ⌘+{, ⌘+}、⌘+`<number>` 切换标签页
- ⌘+F 智能查找，支持正则查找
- `⌘+[`、`⌘+]`、⌘+Option+方向键 切换 pane
- ⌘+D 水平切分屏幕，⌘+Shift+D 垂直切分屏幕
- ⌘+Enter 进入与返回全屏模式

## zsh

```bash
# 主题
ZSH_THEME="powerlevel9k/powerlevel9k"

# 使用nerdfont字体模式
POWERLEVEL9K_MODE="nerdfont-complete"

# 设置左侧信息
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(dir vcs)

# 禁止右侧信息
POWERLEVEL9K_DISABLE_RPROMPT=true

# 换行
POWERLEVEL9K_PROMPT_ON_NEWLINE=true

# 按tab键补全命令的时候,如果没什么可补全的就会出现三个红点,更人性化显示，这里我们启用
COMPLETION_WAITING_DOTS="true"

DISABLE_UNTRACKED_FILES_DIRTY="true"

HIST_STAMPS="yyyy-mm-dd"

plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
  z
)

source $ZSH/oh-my-zsh.sh

# 命令别名
alias art="php artisan"
alias mrs="php artisan migrate:refresh --seed"
alias nrd="npm run dev"
alias nrww="npm run watch-poll"
alias rezsh="source ~/.zshrc"
alias dart="docker-compose exec php php artisan"
alias ll='ls -l'
alias la='ls -a'
alias vi='vim'
```
