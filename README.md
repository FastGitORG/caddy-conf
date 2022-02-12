# caddy-conf

这里是 FastGit 的 Caddy 版本配置,本配置不包含网站反代.

一些 Tips :

- 证书路径按照 `acme.sh` 签发的证书路径来填写.
- 日志,web 文件路径是按照在 docker-compose 下运行来设计的,以当前目录起始

TODOs:

- ~~拆分 raw 和 objects 两个反代~~ 合并到一个文件中处理了
- ~~测试 Caddy 正则表达式路径匹配~~
- [ ] 处理错误重定向
- [ ] 优化&合并配置 (目前完成了部分片段替换)
- [ ] 合并 download 和 archive 配置

由于 Caddy 中不存在 Nginx 的 sub_filter 模块,所以这里需要借助第三方插件

- [sjtug/caddy2-filter](https://github.com/sjtug/caddy2-filter)
- [caddyserver/replace-response](https://github.com/caddyserver/replace-response)

这里选择的是 `situg/caddy2-filter`
