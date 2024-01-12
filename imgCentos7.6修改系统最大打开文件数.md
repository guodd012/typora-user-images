## Centos7.6修改系统最大打开文件数

+ 修改`/etc/systemd/system.conf ` 文件

  ~~~ shell
  vi /etc/systemd/system.conf 
  
  # 文件最后添加以下内容
  DefaultLimitNOFILE=102400
  DefaultLimitNPROC=102400
  ~~~

+ 修改`/etc/security/limits.conf`文件

  ~~~ shell
  vi /etc/security/limits.conf
  # 文件最后添加以下内容
  * soft nofile 102400
  * hard nofile 102400
  * soft nproc 102400
  * hard nproc 102400
  ~~~

+ 重启服务器 `reboot`

+ 检查系统最大打开文件数`ulimit -a`是否修改成102400 

  ![image-20220225141029967](/Users/guodingding/Library/Application Support/typora-user-images/image-20220225141029967.png)

  