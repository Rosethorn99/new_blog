# iBlog
基于 Node.js 的开源个人博客系统，现代化的 UI 和用户体验。支持桌面端和移动端访问，支持深色模式。  
**不仅仅是博客，更是 一个成功的过程**

## 目录
- [界面预览](#界面预览)
- [在线实例](#在线实例)
- [分支说明](#分支说明)
- [技术构成](#技术构成)
- [快速开始](#快速开始)
  * [准备条件](#准备条件)
  * [安装依赖](#安装依赖)
  * [启动站点](#启动站点)
  * [Debug](#debug)
- [系统设置](#系统设置)
- [线上部署](#线上部署)
  * [使用PM2](#使用pm2)
  * [使用noginx](#使用noginx)
- [Docker](#docker)
  * [安装Docker](#安装docker)
  * [制作镜像](#制作镜像)
  * [创建容器](#创建容器)
  * [容器管理](#容器管理)
- [更新日志](#更新日志)
- [TODO](#todo)
- [许可协议](#许可协议)

## 界面预览
* 博客首页
![首页](./preview_1.png)
* 后台管理
![后台](./preview_2.png)

## 在线实例
我的博客 [https://b.abblly.com/](https://b.abblly.com/)

## 技术构成
* 开发语言 [TypeScript](https://www.typescriptlang.org/)
* 服务端 [Node.js](https://nodejs.org/)
* SSR框架 [NuxtJS](https://nuxtjs.org/)
* 前端框架 [Vue](https://vuejs.org/)
* 组件库 [Ant Design of Vue](https://www.antdv.com/docs/vue/introduce-cn/)
* Web字体 [Font Awesome](https://fontawesome.com/)
* 持久化 [MongoDB](https://www.mongodb.org/)
* 身份验证 [@nuxtjs/auth](https://auth.nuxtjs.org/)

## 快速开始

### 准备条件

安装 [Node.js](https://nodejs.org/en/download/) (v8 以上版本)、[MongoDB](https://www.mongodb.org/downloads/)。  
推荐安装 [Yarn](https://yarnpkg.com/) 而非 npm 以进行包管理。

### 安装依赖
```Shell
$ yarn
```

### 启动站点

* 开发模式

```Shell
$ yarn run dev
```

* 生产模式

先编译项目
```shell
$ yarn run build
```

再启动站点
```shell
$ yarn start
```

打开浏览器，访问 [http://localhost:9000/](http://localhost:9000)

### Debug
* 要启动前端代码调试，请直接在 Chrome Dev Tools - Sources 面板中进行。

* 要启动服务端代码调试，请以如下命令启动服务，然后点击 Chrome  Dev Tools 左上角的 Node.js 按钮，就可以像调试前端代码一样调试服务端了。

```shell
$ node --inspect node_modules/.bin/nuxt-ts
```


#### Enjoy it! :smile:

## 系统设置

根据实际情况修改 `/blog.config.ts` 配置文件，修改后需要重启服务器才能生效。  
参数说明：

#### host
`String` 类型，主机名，配置为 `0.0.0.0` 表示监听任意主机。

#### port
`Number` 类型，端口号。

#### enableHTTPS
`Boolean` 类型，是否启用 HTTPS。

#### mongoUrl
`String` 类型，MongoDB 链接。

#### jwtSecret
`String` 类型，[JWT](https://github.com/auth0/node-jsonwebtoken) 秘钥。

## 线上部署

### 使用PM2
推荐使用 [pm2](https://pm2.keymetrics.io/) 进行 Node.js 的进程管理和持久运行。

#### 安装
```Shell
$ yarn global add pm2
```
#### 启动
```Shell
$ pm2 start pm2.json
```
