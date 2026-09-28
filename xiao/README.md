# Ta不懂的数码 · 官网

黑绿科技感的代淘机服务官网，含手机回收 / 销售 / 代淘 / 验机展示，以及可在后台每日更新的「今日好机推荐」。

- 前台首页：`/`
- 管理后台：`/admin.html`（默认密码 `admin123`，生产环境务必通过环境变量修改）
- 零第三方依赖，Node.js ≥ 18

## 本地运行

```bash
node server.js
# 前台 http://localhost:3000  后台 http://localhost:3000/admin.html
```

自定义端口 / 后台密码：

```bash
PORT=8080 ADMIN_PASSWORD=你的密码 node server.js
```

## 一键部署到 Render（免费）

点击按钮，用 GitHub 账号登录 Render，填写后台密码 `ADMIN_PASSWORD`，即可自动部署：

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/REPLACE_OWNER/REPLACE_REPO)

也可在仓库推送后访问：

```
https://render.com/deploy?repo=你的仓库地址
```

部署完成后：

1. Render 会分配 `https://xxx.onrender.com` 域名
2. 打开 `/admin.html`，用设置的密码登录即可每天修改推荐机器
3. 每次 push 到默认分支会自动重新部署

> 说明：免费实例本地 JSON 数据在重新部署时会重置为初始示例。日常修改推荐不受影响；如需跨部署永久保留数据，可后续升级带持久磁盘的实例。

## 目录结构

```
server.js               # 零依赖 Node 服务（静态托管 + API + 鉴权）
public/index.html       # 官网首页
public/admin.html       # 管理后台
public/assets/          # 图片资源
data/recommendations.json  # 每日推荐数据（服务自动生成）
render.yaml             # Render 部署蓝图
```
