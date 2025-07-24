# 气力输送系统选型平台

## 项目概述
这是一个用于气力输送设备选型和系统验算的Web应用平台，帮助用户根据生产需求选择合适的真空加料机型号并进行系统性能验算。

## 本地开发环境

### 前置要求
- Node.js v18+
- pnpm v8+

### 安装依赖
```bash
pnpm install
```

### 启动开发服务器
```bash
pnpm dev
```
应用将运行在 http://localhost:3000

## 构建生产版本(Dist文件夹)

### 本地构建
运行以下命令生成dist文件夹：
```bash
pnpm build
```
构建完成后，dist文件夹将包含所有生产环境所需的静态文件。

### 构建过程说明
1. 清理旧的dist文件夹
2. 使用Vite构建生产版本，输出到dist文件夹
3. 复制package.json到dist目录
4. 创建build.flag文件标记构建完成

## Netlify部署流程

### 准备工作
1. 确保代码已推送到GitHub/GitLab仓库
2. 已创建Netlify账户

### 部署步骤
1. 登录Netlify账户，点击"New site from Git"
2. 选择您的代码仓库
3. Netlify将自动检测到netlify.toml配置文件
4. 点击"Deploy site"开始部署
5. 等待构建完成(约2-3分钟)
6. 获取部署后的URL链接

### 部署配置说明
- 构建命令: `pnpm build` (在netlify.toml中配置)
- 发布目录: `dist` (在netlify.toml中配置)
- Node版本: 18 (在netlify.toml中配置)

## 故障排除

### Dist文件夹未生成
1. 检查是否有编译错误: `pnpm build`
2. 确保所有依赖已安装: `pnpm install`
3. 检查Vite配置是否正确

### Netlify部署失败
1. 检查Netlify构建日志，查看具体错误信息
2. 确保package.json中包含正确的构建脚本
3. 验证netlify.toml配置是否正确
4. 尝试在本地运行`pnpm build`排查构建问题

## 功能说明
- 设备选型: 根据产能、功率等参数筛选合适的真空加料机型号
- 系统验算: 输入输送距离、物料密度等参数，计算系统性能
- 产品详情: 查看设备技术参数、适用行业和特点