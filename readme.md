# Checkin

[注册](https://7m858-dlia3-5j6f6-f30bk.glados.space) 账号

GitHub Actions 实现 [GLaDOS][glados] 自动签到


([GLaDOS][glados] 可用邀请码: `7M858-DLIA3-5J6F6-F30BK`, 双方都有奖励天数)

## 使用说明

1. Fork 这个仓库

1. 登录 [GLaDOS][glados] 获取 Cookie

1. 添加 Cookie 到 Secret `GLADOS`

1. 启用 Actions, 每天北京时间 00:10 自动签到

## 高级功能

1. 如有多个帐号, 可以写为多行 Secret `GLADOS`, 每行写一个 Cookie

1. 如需修改时间, 可以修改文件 [run.yml](.github/workflows/run.yml#L7) 中的 `cron` 参数, 格式可参考 [crontab]

1. 如需推送通知, 可配置 Secret `NOTIFY`, 已支持:
    1. [WxPusher][wxpusher]: 格式 `wxpusher:{token}:{uid}`
    1. [PushPlus][pushplus]: 格式 `pushplus:{token}`
    1. Console: 格式 `console:log`, 作为日志输出, 一般用于调试
    1. 如需配置多个, 可以写为多行, 每行写一个

1. 注意: Cookie 以及接口输出数据, 包含帐号敏感信息, 因此不要随意公开


## 推送
打开 PushPlus, 微信扫码登录

登录后会显示一个 Token, 复制出来

转到 GitHub 打开仓库设置 Settings → Secrets and variables → Actions → New repository secret, 填写完成后保存

Name: NOTIFY

Secret: 前面获取的 Token 值

---

[glados]: https://github.com/glados-network/GLaDOS
[crontab]: https://crontab.guru/
[pushplus]: https://www.pushplus.plus/
[wxpusher]: https://wxpusher.zjiecode.com/
