# API 代理服务

这是一个本地部署的API代理服务，基于Cloudflare Workers脚本改造而来。它保留了原脚本的美观UI界面，同时允许你在自己的服务器上运行API代理服务。

## 功能特点

- 美观的UI界面，展示所有可用的API代理服务
- 支持多种API服务的代理，包括OpenAI、Gemini、Claude、Grok等
- 完全本地部署，无需依赖Cloudflare Workers
- 简单易用，配置灵活

## 安装与使用

### 前提条件

- Node.js (推荐v14或更高版本)
- npm 或 yarn

### 安装步骤

1. 克隆或下载本仓库到你的服务器

2. 安装依赖
   ```
   npm install
   ```

3. 启动服务
   ```
   npm start
   ```

4. 访问服务
   
   打开浏览器，访问 `http://你的服务器IP:3000` 即可看到API代理服务的界面

### 开发模式

如果你想在修改代码后自动重启服务，可以使用开发模式：

```
npm run dev
```

## 配置说明

你可以在`server.js`文件中的`API_CONFIGS`对象中修改或添加API服务配置：

```javascript
const API_CONFIGS = {
  服务名称: {
    host: '目标API主机名',
    paths: ['API路径前缀'],
    description: "服务描述",
    logo: "服务图标(emoji)",
    directUrl: true/false  // 是否直接使用目标URL而不是代理URL
  }
}
```

## 部署建议

在生产环境中，建议：

1. 使用PM2等进程管理工具来管理Node.js应用
2. 配置Nginx等Web服务器作为反向代理
3. 设置SSL证书以启用HTTPS
4. 根据需要调整服务器防火墙规则

## 许可证

MIT