# 妙邮 / Meowmail for LazyCat

这是 [妙邮（Meowmail）](https://github.com/ca-x/meowmail) 的懒猫微服 LPK 发布仓库。

妙邮是一个由 Rust 后端和 React 前端组成的自托管 Web 邮件客户端，支持多个邮件账户、SQLite 本地存储，以及为每个邮件账户独立配置 HTTP 或 SOCKS5 代理。

![妙邮工作区](https://raw.githubusercontent.com/ca-x/meowmail/main/docs/assets/screenshots/workspace.png)

## 安装参数

- `妙邮 PIN 码`：用于 `/login` 登录，同时参与邮件账户凭据的服务端加密。安装向导默认生成随机值，登录页会由懒猫注入自动填写并提交。
- `时区`：IANA 时区名称，默认 `Asia/Shanghai`。

应用启用了多实例模式，每位懒猫用户拥有独立容器和独立的 `/data` 持久化目录。

## 自动发布

`.github/workflows/lazycat.yml` 使用 `ca-x/lazycat-github-action@v1`：

- 监控 `docker.io/czyt/meowmail` 的稳定版本；
- 将 amd64 镜像复制到懒猫镜像仓库；
- 构建版本化 LPK GitHub Release 资产；
- 分别发布到懒猫官方商店和 MiaoMiao 私有商店；
- 已存在相同或更高版本时安全跳过。

## 相关链接

- 源代码：https://github.com/ca-x/meowmail
- LazyCat 发布仓库：https://github.com/lazycat-contrib/meowmail
- 首个上游版本：https://github.com/ca-x/meowmail/releases/tag/v0.1.0

## License

MIT
