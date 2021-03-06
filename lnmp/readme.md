## lnmp环境独立安装脚本.

> 可在ECS的CentOS7.0-64bit系统(标准镜像)中可靠运行。

> 推荐运行顺序(非强制)：  
> `提示: 当遇到提示你的系统缺少某个库时, 用yum安装好依赖, make clean 之后再执行一次安装脚本`  

>    installMysql.sh  
>    `curl -sS https://raw.githubusercontent.com/farwish/delicateShell/master/lnmp/installMysql.sh | sh`  

>    installNginx.sh  
>    `curl -sS https://raw.githubusercontent.com/farwish/delicateShell/master/lnmp/installNginx.sh | sh`  

>    installPhpUseDefaultLibpng.sh  
>    `curl -sS https://raw.githubusercontent.com/farwish/delicateShell/master/lnmp/installPhpUseDefaultLibpng.sh | sh`  

>    installRedis.sh  
>    `curl -sS https://raw.githubusercontent.com/farwish/delicateShell/master/lnmp/installRedis.sh | sh`  

>    installPhalcon.sh  
>    `执行前, 将extension=phalcon.so加入php.ini, 因为脚本将扩展和开发工具一起装了, 开发工具又依赖扩展, 所以提前加好`  
>    `curl -sS https://github.com/farwish/delicateShell/blob/master/lnmp/installPhalcon.sh | sh`  

## 管理.

> [ redis ]

> /usr/local/redis/bin/redis-server /usr/local/redis/etc/redis.conf

```
// Usage: redis start|stop|restart|status  
// `cp /etc/init.d/redis_6379 /usr/local/redis/bin`  
// `redis start` # 启动redis  
```

--

> [ mysql ]

> Usage: mysql.server  {start|stop|restart|reload|force-reload|status}  [ MySQL server options ]

> `mysql.server start` # 启动 mysql

--

> [ php-fpm ]

> Usage: init.d.php-fpm {start|stop|force-quit|restart|reload|status}

> `init.d.php-fpm start` # 启动 php-fpm

--

> [ nginx ]

> Usage: nginx [-?hvVtTq] [-s signal] [-c filename] [-p prefix] [-g directives]

> `nginx`  # 启动 nginx；安装时已制定配置文件，所以可以省略制定配置文件  
> `nginx -s reload` # 重载工作进程，使配置生效  
> `pkill -9 nginx` # 关闭 nginx  

--
