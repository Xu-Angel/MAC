# 开发效率提升之工具篇

### 导读

[打造舒适高效的前端开发环境](https://fe.surge.sh/guide/)

[mac OS 使用手册](https://support.apple.com/zh-cn/guide/mac-help/mh35835/mac)

[Awesome Mac](https://github.com/jaywcjlove/awesome-mac/blob/master/README-zh.md)

[开发效率提升：Mac生产力工具链推荐](https://github.com/Louiszhai/tool)

[Mac系统、Mac软件的操作和使用技巧整理，正在不断完善中。努力做到最全](https://github.com/qianguyihao/Mac)

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

### 软件

- [大黄鸭](https://cyberduck.io/)  Cyberduck is a libre server and cloud storage browser for Mac and Windows with support for FTP, SFTP, WebDAV, Amazon S3, OpenStack Swift, Backblaze B2, Microsoft Azure & OneDrive, Google Drive and Dropbox