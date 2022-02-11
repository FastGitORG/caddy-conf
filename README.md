# caddy-conf

这里是 FastGit 的 Caddy 版本配置,本配置不包含网站反代.

一些 Tips :

- 证书路径按照 `acme.sh` 签发的证书路径来填写.
- 日志,web 文件路径是按照在 docker-compose 下运行来设计的,以当前目录起始

TODOs:

- [ ] 测试Caddy正则表达式路径匹配
- [ ] 处理错误重定向
- [ ] 优化&合并配置