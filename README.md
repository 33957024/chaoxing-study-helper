# 💯 超星学习通助手

基于 [shushoujiu](https://greasyfork.org/scripts/436994) 原版二次开发的学习通自动答题油猴脚本，接入火山方舟 AI（豆包/DeepSeek），支持联网搜索。

## ✨ 功能

- 🤖 **AI 自动答题**：接入火山方舟，默认 `doubao-seed-evolving`，支持单选/多选/判断/填空/简答/名词/论述/计算
- 🔍 **豆包联网搜索**（可选开关）：Responses API + `web_search` tool，实时联网检索答案
- 🔁 **AI 请求 60s 超时 + 失败重试 3 次**，偶发抖动先重试，连续失败才自动降级
- 🎬 **任务点自动完成**：视频/音频静音播放、自动跳转章节
- 🧠 **章节测验/作业/考试自动答题**：先自定义题库 → 再 AI 兜底
- 🔄 **每 5 个任务点回补扫描**：防止学习通懒加载漏题
- 🎛️ **可视化参数配置**：独立「AI能力」tab，开关/Key/模型名一目了然

## 📦 安装

### 前置要求
1. 浏览器装 [Tampermonkey](https://www.tampermonkey.net/) 扩展
2. 一个火山方舟 API Key（[console.volcengine.com](https://console.volcengine.com)）
   - 套餐用户直接用 Model ID（如 `doubao-seed-evolving`），不需要 ep- 接入点

### 安装脚本
1. 打开本仓库的 `超星学习通助手.user.js` 文件
2. 点右上角「Raw」按钮 → Tampermonkey 会弹安装确认 → 点「安装」
3. 打开任意学习通页面 → 点右下角 💯 按钮 → 切到「AI能力」tab
4. 填入：
   - **AI API 地址**：`https://ark.cn-beijing.volces.com/api/v3/chat/completions`
   - **AI API Key**：你的火山 API Key
   - **AI 模型名**：`doubao-seed-evolving`
   - **启用 AI 自动答题**：打开
   - **启用豆包联网搜索**：按需打开（需先在火山控制台开通「豆包搜索」组件）
5. 保存 → 刷新页面

## 🔄 自动更新

脚本头已配置：

```js
// @updateURL  https://raw.githubusercontent.com/33957024/chaoxing-study-helper/main/超星学习通助手.user.js
// @downloadURL https://raw.githubusercontent.com/33957024/chaoxing-study-helper/main/超星学习通助手.user.js
```

Tampermonkey 会**每天自动检查 `@version` 号**，发现新版自动下载安装。你不需要手动重装。

### 发版流程（维护者）
1. 改代码
2. 脚本头 `@version` 升号（`1.0.0 → 1.0.1`）
3. `notice` 和弹窗 `msg` 里的版本号同步更新
4. `git commit && git push`

Tampermonkey 下次自动检查时就会发现新版本。

## 📁 仓库结构

```
chaoxing-study-helper/
├── 超星学习通助手.user.js   # 主脚本（油猴直接加载这个）
├── README.md
└── LICENSE
```

## ⚠️ 免责

本脚本仅供学习交流使用，严禁用于商业用途，24h 内删除，后果自负。

## 📄 License

MIT
