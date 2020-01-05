# 开发效率提升之工具篇

### 导读

[mac OS 使用手册](https://support.apple.com/zh-cn/guide/mac-help/mh35835/mac)

### 支持NTFS

- 原生方式

  ```bash
  diskutil list // 显示挂载情况
  sudo vim /etc/fstab // 编辑
  LABEL=HD-E1 none ntfs rw,auto,nobrowse  // 对名字叫做HD-E1的硬盘开启支持
  sudo ln -s /Volumes ~/Desktop/Volumes
  LABEL=视频 none ntfs rw,auto,nobrowse
  LABEL=文档 none ntfs rw,auto,nobrowse
  LABEL=系统 none ntfs rw,auto,nobrowse
  LABEL=其他 none ntfs rw,auto,nobrowse
  LABEL=装装 none ntfs rw,auto,nobrowse
  LABEL=包包 none ntfs rw,auto,nobrowse
  LABEL=料料 none ntfs rw,auto,nobrowse
  ```

- 使用希捷自带的免费Paragon NTFS for Mac

### 显示安全性与隐私的任何来源

```bash
sudo spctl --master-disable
```

### Mac重度依赖者

#### 开发工具

- [Charles](https://www.charlesproxy.com/) 网络抓包应用, mac必备.
- [aText](http://www.trankynam.com/atext/) 输入增强应用, 比 [`TextExpander`](http://www.pc6.com/mac/146924.html) 要人性化许多，并且对中文和第三方输入法的支持都要更好.
- [Dash](https://kapeli.com/dash) mac上api集合应用, 几乎包含各种语言的api文档.
- [SnippetsLab](http://www.renfei.org/snippets-lab/) 优秀的代码片段管理工具, 轻量, 可基于菜单栏操作.
- [CodeExpander](https://codeexpander.com) 专为开发者开发的一个集输入增强、代码片段管理(支持 Markdown)为一体跨平台云同步的开发工具。

#### 效率提升

- [Alfred 3](http://www.sdifenzhou.com/alfred3.html) 神奇的魔法帽, 支持 ① 快速打开application; ② 支持Finder, Calculator, Contacts, Clipboard, iTunes, System, Terminal 等原生应用的各种便捷功能; ③ 支持workflow(工作流)(需要升级为收费版的Powerpack).
- [iterm2](http://www.iterm2.com/) 增强版的终端应用, 功能强大, 支持分屏, 历史记录, 选中即复制等.
- [Sip](http://www.pc6.com/mac/124262.html) 全屏取色应用, 支持快捷键调出(前端福音, 寻找多年, 终于发掘出来了).
- [Keka](http://www.kekaosx.com/en/) 压缩或解压缩应用, 开源免费, 压缩比高, 操作便捷, 支持rar等解压, 压缩中文目录后, 在windows下打开不会存在乱码等现象.
- [Scroll Reverser](http://pilotmoon.com/scrollreverser/) mac滚动方向自定义应用, 可分别设置鼠标和触摸板的上下左右的滚动效果.
- [Size up](http://www.irradiatedsoftware.com/sizeup/) 分屏应用, 类似Moon的一款应用, 支持上下左右居中、4个角落快速分屏及多屏幕切换.
- [Divvy](http://www.pc6.com/mac/124992.html) 另一款分屏应用, 可将屏幕分成多宫格的形式, 然后为每个格子定义快捷键, 遗憾的是不支持多屏幕切换.
- [Graphviz](http://www.graphviz.org/) 贝尔实验室开发的有向图/无向图自动布局应用, 支持dot脚本绘制结构图, 流程图等. 可参考教程 [利用Graphviz 画结构图](http://www.cnblogs.com/sld666666/archive/2010/06/25/1765510.html) 及 [使用graphviz绘制流程图](http://www.cnblogs.com/CoolJie/archive/2012/07/17/graphviz.html) .
- [XMind](http://www.xmindchina.net/) 思维导图应用, 适合业务及思路梳理.
- [iThoughtsX](http://www.pc6.com/mac/129882.html) 另一款思维导图应用, 更加简洁和轻量.
- [Pomodoro One](http://www.pc6.com/mac/136806.html) 番茄工作法的一款应用.
- [Recess](http://imacami.net/#rss)规范时间的软件

#### 博主必备

- [ScreenFlow](http://screenflow.en.softonic.com/mac) 这或许是mac上最好用的屏幕录制应用.
- [Snipaste](https://zh.snipaste.com/)或许是最好的截图软件
- [Annotate](http://www.waitsun.com/annotate-2-0-5.html) 屏幕截图批注应用, 令人惊喜的是, 支持划区域gif制作, 教程以及动图制作者必备.
- [Licecap](http://www.cockos.com/licecap/) mac上超强大的且极简的gif录制应用, 使用免费, 支持FPS帧率调整且无录制时间限制(笔者用它录制了很多gif动图).
- [KeyCastr](http://mac.softpedia.com/get/Utilities/KeyCastr.shtml) 将mac按键显示在屏幕上，分享演示、录制视频或动图时超赞.

#### Mac定制化

- [Bartender 3](https://www.macbartender.com/) 菜单栏管理应用, 支持隐藏所有菜单栏图标, 还您一个干净的菜单栏.
- [Dozer](https://github.com/Mortennn/Dozer) 隐藏菜单栏项目,功能类似Bartender但是开源免费
- [CDock](http://www.pc6.com/mac/161158.html) 任务栏定制应用, 可设置Dock全透明, 还您一个清爽的任务栏.
- [TextBar](https://www.macstories.net/mac/textbar-puts-your-text-into-the-menu-bar/) 自定义菜单栏输出, 支持script运行, 支持H5渲染.
- [Growl](http://growl.info/) 自定义通知样式, 支持多种主题以及颜色, 大小, 渐隐时间等各项参数的自定义.
- [Karabiner](https://pqrs.org/osx/karabiner/) 键盘映射修改神器.
- [Magnet](https://magnet.crowdcafe.com/index.html)窗口管理工具，提升工作效率
- [Keyboard Maestro](https://www.keyboardmaestro.com/main/) 键盘大师, mac下功能最为丰富的键盘增强应用.
- [BetterTouchTool](https://www.boastr.net/) mac触摸板增强神器.
- [Übersicht](http://sspai.com/28020) 华丽的桌面自定义应用, 类似于windows的 [`rainmeter`](http://rainmeter.cn/cms/). 支持H5.
- [Today Scripts](http://www.waerfa.com/today-scripts-for-yosemite-today-view) 个性化通知栏插件, 支持bash脚本.
- [Mountain Tweaks](http://tweaksapp.com/app/mountain-tweaks/) mac隐藏功能开启应用.

#### 折腾党玩转Mac

- [TripMode](http://www.pc6.com/mac/144495.html) 移动热点流量管家, 出差达人的福音.
- [Caffeine](http://www.pc6.com/mac/121734.html) 点亮mac, 避免长时间演示ppt而进入到休眠状态.
- [Tickeys](http://www.yingdev.com/projects/tickeys) 键盘打字风格模拟应用, 支持 Cherry轴等多种风格.
- [keycue](http://www.pc6.com/mac/116332.html) 快捷键辅助应用, 帮助记忆快捷键.
- [AirServer](http://www.airserver.com/) IOS连接mac必备.
- [Beyond Compare](http://www.beyondcompare.cc/) 文件比较应用, 支持文件, 目录, FTP远程地址比较等.
- [Debookee](http://www.pc6.com/mac/129593.html) 网络抓包及数据分析应用.
- [EasyFind](http://www.waerfa.com/easyfind) 小而强大的文件搜索应用, 媲美windows下的Everything.
- [FileZilla](https://filezilla-project.org/) 免费开源的FTP应用.
- [OmniDiskSweeper](http://newping.cn/322) 硬盘空间扫描应用, 帮助mac减肥.
- [Kaleidoscope](http://www.pc6.com/mac/113361.html) 文件和图像比较应用, 支持图片比较, 能与 git, svn 等版本控制工具完美结合.
- [AppCleaner](http://freemacsoft.net/appcleaner/) mac应用卸载工具, 结合  [`AppCleaner`](https://github.com/Louiszhai/tool/blob/master/workflow/AppCleaner.alfredworkflow?raw=true) 的workflow, 使用效果更佳.
- [TeamViewer](http://www.pc6.com/mac/115425.html) 远程开发或协助必备应用. 
- [Script Debugger](http://www.pc6.com/mac/428096.html) 强大的AppleScript编辑器.
- [Reeder](http://www.pc6.com/mac/158839.html) 界面优美的RSS订阅应用.
- [HyperSwitch](https://bahoom.com/hyperswitch) 带有预览图的快速切换, 作用同Command+Tab.
- [Fruit Juice](http://www.pc6.com/mac/119197.html) 电池管理应用, 帮助延迟电池的使用时间.

### Chrome Extension篇

- [谷粒Chrome插件英雄榜](https://github.com/zhaoolee/ChromeAppHeroes) chrome优秀插件合集

#### Chrome Extension开发

相关文章

- [Sample Extensions - Google Chrome](https://developer.chrome.com/extensions/samples)
- [图灵社区: 合集 : Chrome扩展及应用开发](http://www.ituring.com.cn/minibook/950)
- [Google Chrome扩展开发系列](http://www.cnblogs.com/champagne/tag/Google%20Chrome%E6%89%A9%E5%B1%95/)