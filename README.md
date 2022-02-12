# caddy-conf

这里是 FastGit UK 的 Caddy 版本配置，本配置暂不包含网站反代

> 项目暂停,因为 Caddy 不支持反向代理中跟随重定向,这破坏了在 download 子域中直接实现下载而不需要跳转的特性

## 一些 Tips

- 证书路径按照 `acme.sh` 签发的证书路径来填写
- 日志，web 文件路径是按照在 `docker-compose` 下运行来设计的，以当前目录起始
- 由于做了合并,日志文件按照以下路径保存
  - raw 和 objects 保存为 raw.fastgit.org.log
  - download 和 archive 保存为 download.fastgit.org.log

## TODOs

- [x] 拆分 raw 和 objects 两个反代
- [x] 测试 Caddy 正则表达式路径匹配
- [x] 优化 & 合并配置 (目前完成了部分片段替换)
- [x] 合并 download 和 archive 配置
- [ ] 去写个 Caddy 模块来使 Caddy 支持代理中跟随重定向
- [ ] 动态更换重写地址中的端口
- [ ] 处理错误重定向
- [ ] 处理错误页面

由于 Caddy 中不存在 Nginx 的 `sub_filter` 模块，所以这里需要借助第三方插件

- [sjtug/caddy2-filter](https://github.com/sjtug/caddy2-filter)
- [caddyserver/replace-response](https://github.com/caddyserver/replace-response)

本仓库使用的是 `situg/caddy2-filter`
