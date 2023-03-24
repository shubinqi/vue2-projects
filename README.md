<!--
 * @Author: Shu Binqi
 * @Date: 2023-03-11 19:16:02
 * @LastEditors: Shu Binqi
 * @LastEditTime: 2023-03-12 12:32:07
 * @Description: Vue 2.X 参考项目
 * @Version: 1.0.0
 * @FilePath: \interviewQuestionsd:\Git\vue2-projects\Readme.md
-->

## 运行环境

### 安装必备软件

1. NodeJS：安装 Nodejs 环境（如果需要可切换版本安装 NVM）
2. Git：安装版本管理工具
3. VS Code：编辑器软件

检查环境：

```
# Node 是否安装完成
node -v

# npm 是否可以使用
npm -v

# cnpm 是否可以使用
cnpm -v

# yarn 是否可以使用
yarn -v

# Vue 脚手架是否可以使用
vue -V
```

### 安装必备依赖

```
# 查看当前镜像
npm get registry

# 修改 npm 源为 淘宝镜像
npm config set registry https://registry.npmmirror.com

# 安装最新版 Vue 脚手架
npm install @vue/cli -g
```

## 创建 Vue 2.X 项目

### 创建 Vue 2.X + Element-UI 项目（管理系统）

> 具体技术栈：Vue 2.X + Vue-Router + Element-UI + VueX + axios

1. 使用 Vue-Cli

```
# 创建项目
vue create vue2-element--cli

# 新增依赖 Vue-Router + Element-UI + VueX + axios

# <!-- 单个安装 -->
npm install vuex
npm install vue-router
npm install axios
npm install element-ui

# 批量安装
npm install vuex vue-router axios element-ui

# 启动项目
npm run serve

# 打包项目
npm run build
```

2. 使用 Webpack

```
vue init webpack vue2-element-webpack
```

注意事项：

- 项目名称不能包含大写字母。

### 创建 Vue 2.X + jQuery 项目（网站）

> 具体技术栈：Vue 2.X + Vue-Router + jQuery + VueX + axios

### 创建 Vue 2.X + Vant-UI 项目（H5）

> 具体技术栈：Vue 2.X + Vue-Router + Vant-UI + VueX + axios
