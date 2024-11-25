# 开发效率提升之工具篇

### 导读

[打造舒适高效的前端开发环境](https://fe.surge.sh/guide/)

[mac OS 使用手册](https://support.apple.com/zh-cn/guide/mac-help/mh35835/mac)

[Awesome Mac](https://github.com/jaywcjlove/awesome-mac/blob/master/README-zh.md)

[开发效率提升：Mac 生产力工具链推荐](https://github.com/Louiszhai/tool)

[Mac 系统、Mac 软件的操作和使用技巧整理，正在不断完善中。努力做到最全](https://github.com/qianguyihao/Mac)

### 支持 NTFS

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

- 使用希捷自带的免费 Paragon NTFS for Mac

### 显示安全性与隐私的任何来源

```bash
sudo spctl --master-disable
```

### 软件

- https://macwk.cn/
- [大黄鸭](https://cyberduck.io/) Cyberduck is a libre server and cloud storage browser for Mac and Windows with support for FTP, SFTP, WebDAV, Amazon S3, OpenStack Swift, Backblaze B2, Microsoft Azure & OneDrive, Google Drive and Dropbox
- [日历-Itsycal for Mac](https://www.mowglii.com/)
- Downine 4 && Permute3
- sensei 系统监控
- pap.er
- IINA
- [Magnet 窗口智能管理工具](https://macwk.cn/app/476.html)
- Bitcomet
- cheatsheet
- Qspace
