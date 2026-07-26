# 妙邮（Meowmail）for LazyCat

这是 [妙邮（Meowmail）](https://github.com/ca-x/meowmail) 的懒猫微服 LPK 发布仓库。

妙邮是一个由 Rust 后端和 React 前端组成的多用户 Web 邮件客户端。它支持多个邮件账户、SQLite 本地存储、账户级 HTTP/SOCKS5 代理、个人邮件清理规则，以及按类型选择的用户配置导入与导出。

![妙邮工作区](https://raw.githubusercontent.com/ca-x/meowmail/main/docs/assets/screenshots/workspace.png)

## 安装参数

- `时区`：IANA 时区名称，默认 `Asia/Shanghai`。

应用采用单实例多用户模式，并仅启用懒猫 OIDC 登录。首位登录且系统中尚无管理员的 OIDC 用户会成为管理员；之后的用户以普通用户身份加入。每位用户的邮件账户、偏好、清理规则和导入导出数据均由妙邮隔离。

个人 PIN 仍可在妙邮内设置，用于用户主动锁定后的再次认证，不作为懒猫入口登录凭据。邮件账户凭据使用安装级稳定密钥加密，SQLite、密钥材料和本地邮件副本保存在 `/lzcapp/var/data`，服务以 `root` 用户运行以兼容懒猫持久目录挂载。

配置导入、导出和附件文件操作已接入懒猫文件选择器，可选择本地设备或懒猫网盘。

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
- 当前上游版本：https://github.com/ca-x/meowmail/releases/tag/v0.2.0

## License

MIT
