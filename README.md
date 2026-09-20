# Infinite Archive V2

结构：
- `index.html`：GitHub Pages 阅读器
- `worker.js`：Cloudflare Worker，负责从公开 AO3 work 页面读取标题、作者、简介和正文 HTML
- `README.md`：部署说明

部署：
1. 把 `index.html` 放进 GitHub Pages 仓库根目录。
2. 在 Cloudflare Workers & Pages 创建一个 Worker，把 `worker.js` 全部粘进去并部署。
3. 复制 Worker 地址，例如 `https://xxx.xxx.workers.dev`。
4. 打开 `index.html` 顶部“设置”，把“AO3 抓取服务地址”填成这个 Worker 地址。
5. 输入 AO3 的公开作品链接，点击“导入”。

注意：
- 这是读取公开可访问页面的个人阅读工具，不绕过 AO3 登录、年龄/访问限制或 Cloudflare 验证。
- 如果某个作品需要登录或 AO3 拒绝 Worker 请求，页面会明确显示失败原因。
- 作品正文默认保存在浏览器 localStorage，不上传到第三方数据库。
