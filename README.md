# ChatGPT Plus 订阅教程 - Vue 3 项目

这是一个使用 Vue 3 构建的 ChatGPT Plus 订阅指南网站。该项目提供了详细的步骤和指南，帮助用户开通 ChatGPT Plus 会员服务。

## 项目特点

- 使用 Vue 3 构建
- 组件化设计，易于维护
- 响应式布局，适配移动端设备
- 简洁明了的用户界面

## 如何运行

1. 安装依赖
```bash
npm install
```

2. 启动开发服务器
```bash
npm run serve
```

3. 构建生产版本
```bash
npm run build
```

## 项目结构

```
chatgpt-plus-vue/
├── public/              # 静态资源
├── src/                 # 源代码
│   ├── assets/          # 资源文件 (CSS, 图片等)
│   ├── components/      # 组件
│   ├── App.vue          # 主组件
│   └── main.js          # 入口文件
├── index.html           # HTML 模板
├── package.json         # 项目依赖
├── vite.config.js       # Vite 配置
└── README.md            # 项目文档
```

## 组件说明

- `AppHeader`: 页面标题和副标题
- `OverviewSection`: 显示订阅流程的概览卡片
- `StepsSection`: 详细的步骤指南
- `FaqSection`: 常见问题解答
- `AppFooter`: 页面底部信息

## 技术栈

- Vue 3
- Vite
- CSS3 (原生CSS，无外部依赖) 