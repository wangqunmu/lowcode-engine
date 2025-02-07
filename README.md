# 低代码引擎

## 开发

### 环境
需要`Node.js 16+`（但是需要<18），如`16.20.2`

### 安装

```bash
# clone仓库到本地
git clone git@github.com:alibaba/lowcode-engine.git
cd lowcode-engine

# 安装依赖
npm install && npm run setup
```

### 本地调试流程

> 需要将 demo 页面引入的几个 js/css 代理到 engine 项目，可以使用chrome插件 [XSwitch](./tools/xswitch.crx) 完成

1. 配置`XSwitch`代理规则并保持开启：

```json
{
  "proxy": [
    [
      "https://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/js/engine-core.js",
      "http://localhost:5555/js/AliLowCodeEngine.js"
    ],
    [
      "https://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/css/engine-core.css",
      "http://localhost:5555/css/AliLowCodeEngine.css"
    ],
    [
      "https?://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/js/react-simulator-renderer.js",
      "http://localhost:5555/js/ReactSimulatorRenderer.js"
    ],
    [
      "https?://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/css/react-simulator-renderer.css",
      "http://localhost:5555/css/ReactSimulatorRenderer.css"
    ],
    [
      "https?://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/js/rax-simulator-renderer.js",
      "http://localhost:5555/js/RaxSimulatorRenderer.js"
    ],
    [
      "https?://uipaas-assets.com/prod/npm/@alilc/lowcode-engine/(.*)/dist/css/rax-simulator-renderer.css",
      "http://localhost:5555/css/RaxSimulatorRenderer.css"
    ],
  ]
}
```

2. 执行`npm start`
3. 访问[测试网址](https://lowcode-engine.cn/demo/demo-general/index.html)开始调试
