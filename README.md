# omikuji

# 一签 · Omikuji

独立的 React + Vite 项目，与 `/workspace/my-first-website` 无关。无需账号、密钥或后端。

## 开发

在终端进入本目录，然后执行：

```sh
cd /path/to/omikuji
npm ci --cache /tmp/omikuji-npm-cache
npm run dev -- --port 5173
```

浏览器在运行命令的同一台电脑访问 http://localhost:5173 。云机器的 localhost 不能在手机上直接访问；本项目未部署。

## 正式构建

```sh
npm run build
npm run preview -- --port 4173
```

构建产物在 `dist`，可用任意静态文件服务器提供；不需外部 API。运行时资源全部来自本项目，断开外网仍可抽签。刷新会清除问题和结果，不保存个人信息。

## 内容与交互

- `src/fortunes.js`：28 条原创签文、签号、运势与本地建议规则。4 大吉、6 吉、6 中吉、5 小吉、4 末吉、3 凶。
- `src/main.jsx`：准备 → 摇签 → 抽签 → 结果的状态机；开始时只随机一次，使用同步锁防止重复触发。
- `src/style.css`：和纸风格、木质签筒插画及分层动画、移动端与减少动态效果适配。
- Enter 只在问题框内换行。空问题表示今日运势。
- 分享优先使用系统分享，否则复制；权限失败会显示可手动复制的文本。分享时会包含所填问题，请自行选择分享对象。
- 签文并非寺院真实签文，不作未来预测。分类建议来自预写文本。

使用 GitHub Actions 构建并发布到 GitHub Pages。请在 Settings → Pages → Source 选择 GitHub Actions。
