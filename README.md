# Break-space · 破界

Designed for sales professionals, presales teams, and forward-deployed engineers (FDEs) entering new industry verticals.

原生 HTML / CSS / JavaScript 单文件应用，无构建、无第三方依赖。输入行业，确认边界，自动执行四步分析，再进行可选的 15 轮模拟从业者访谈和知识诊断。支持流式输出、报告导出、停止、失败重试、来源链接和 token 用量。

## 使用

打开网页，点击「设置」，填入自己的 API Key。默认服务商为小米 MiMo，模型 `mimo-v2.6-pro`，地址 `https://api.xiaomimimo.com/v1`。修改 API Key 或模型名均在设置中完成，无需改代码。也支持 Anthropic、OpenRouter 和兼容接口。

Key 只保存在当前页面内存，不写入源码、报告或浏览器 localStorage。刷新后需要重新填写。报告及不含 Key 的设置可保存在当前浏览器。模型调用由浏览器直接发往所选服务商，需要服务商允许跨域请求。此仓库不包含任何私人密钥。

「先体验完整流程」使用内置演示，不调用 API、不产生模型费用。

## 发布到 GitHub Pages

1. 此项目已准备为 GitHub 仓库 `a0912715960-sys/Break-space` 的根目录静态网页，入口为 `index.html`。
2. 在仓库 Settings → Pages → Build and deployment 中，Source 选择 **GitHub Actions**。
3. 默认分支为 `main` 时，推送会自动触发部署；也可以在 Actions → Deploy Pojie to Pages 中手动运行。
4. 部署成功后，从 Settings → Pages 获取实际网址。之后修改文件并推送即可更新。

如果默认分支不是 `main`，修改 `.github/workflows/pages.yml` 的 branches。若组织政策禁止 Actions/Pages，需要仓库管理员启用。

此包同时兼容 Pages 的分支发布方式：Source 选择 Deploy from a branch，选主分支与根目录即可；无需运行构建。

## 证据与联网

内置 System 与 Step 0–5 提示词保留原文，可在左侧查看、复制。联网核实默认关闭；没有真实检索时不能将记忆标为 A 档证据。MiMo 联网插件需要相应服务权限，当前此前实测返回 HTTP 400，因此未宣称联网取证可用。模型的事实、来源和证据等级仍应核验。

网络断开后按最近完整响应检查点重试，替换未完成片段；不是服务器字节级续传，重试可能产生额外费用。模拟访谈不能替代真实从业者访谈。

## 本地运行

直接打开 `index.html` 即可手动填写 Key 体验。也可使用任意静态网页服务器。Windows 本机加密记住 Key 的启动工具包含在单独的本地版下载包中，不属于此 GitHub 发布包。
