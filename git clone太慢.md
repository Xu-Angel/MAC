
# 适用各种操作系统

- 查找域名对应的ip地址，并修改hosts文件

  ```bash
  nslookup github.global.ssl.fastly.Net
  nslookup github.com
  ```

  将ping 到的answer 下的Address 加到 /etc/hosts中

  Windows上的hosts文件路径在C:\Windows\System32\drivers\etc\hosts

  *nux的hosts文件路径在：sudo vim /etc/hosts
  
  ```bash
  151.101.76.249 http://global-ssl.fastly.net
  192.30.255.113 http://github.com  #此处112还是113根据自己的情况调整？
  ```

- 刷新DNS缓存

  linux：
  ```bash
  sudo /etc/init.d/networking restart
  ```

  windows：
  ```bash
  ipconfig /flushdns
  ```

  mac：
  ```bash
  sudo killall -HUP mDNSResponder
  ```

- 设置终端代理