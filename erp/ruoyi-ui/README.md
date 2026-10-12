# ERP 企业管理平台前端

本工程位于统一仓库的 `erp/ruoyi-ui/`，项目说明见 [ERP README](../README.md)。以下开发命令从统一仓库根目录执行，发布命令在前端目录执行。

## 开发

```bash
# 从统一仓库根目录进入 ERP 前端
cd erp/ruoyi-ui

# 安装依赖
npm install

# 建议不要直接使用 cnpm 安装依赖，会有各种诡异的 bug。可以通过如下操作解决 npm 下载速度慢的问题
npm install --registry=https://registry.npmmirror.com

# 启动服务
npm run dev
```

浏览器访问 http://localhost:80

## 发布

```bash
# 构建测试环境
npm run build:stage

# 构建生产环境
npm run build:prod
```
