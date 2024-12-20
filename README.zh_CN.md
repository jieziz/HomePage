---

# 戒子 - HomePage

[English Version](README.md)

## 项目简介

`戒子` 是一个酷炫的个人主页项目，展示了丰富的功能和优雅的设计。项目使用了现代化的前端技术栈，包括 WebGL 背景、SCSS、Pug 和 Gulp 构建工具。

[在线浏览](http://jesz.org)

## 必备条件

在开始之前，请确保你的开发环境满足以下要求：

- **Node.js**：6.0 或更高版本
- **Git**：已安装并可用

## 安装步骤

按照以下步骤快速启动项目：

```sh
# 克隆项目
git clone https://gitee.com/jiezzz/HomePage.git

# 进入项目目录
cd HomePage

# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

## 常见问题与修复

在某些情况下，安装过程中可能会遇到依赖问题。以下是解决方案：

```sh
# 1. 安装 cnpm（淘宝镜像）
npm install -g cnpm --registry=https://registry.npm.taobao.org

# 2. 删除 package.json 中的 node-sass 和 gulp-sass
cnpm install node-sass --save-dev
cnpm install gulp-sass --save-dev

# 3. 安装其他依赖
cnpm install

# 4. 安装 sass
cnpm install sass --save-dev
```

## 功能特性

`戒子` 主页具备以下亮点：

1. **高度封装**：所有页面信息均经过精心封装，便于维护和扩展。
2. **WebGL 背景**：使用 [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) 实现动态背景效果。
3. **SCSS 预处理器**：采用 SCSS 编写样式，提升开发效率。
4. **Pug 模板引擎**：使用 Pug 作为 HTML 预处理器，简化页面结构。
5. **Gulp 构建工具**：已配置好构建脚本，支持自动化构建。
6. **动画与 UI**：提供流畅的动画效果和美观的用户界面。
7. **响应式设计**：无缝支持移动端设备。
8. **轻量级资源**：所有引用的 CSS 和 JS 文件总大小不超过 18.5 KB。
9. **延迟响应**：优化页面切换事件，提升用户体验。
10. **更多特性**：等待你来探索！

## 项目结构

项目根据功能分为两大模块：

1. **`intro`**：首屏内容
2. **`main`**：副屏内容

相应的函数、样式和配置文件均按照此结构组织。

## 基本配置

项目的配置文件为 `config.json`，其中的每一项键名与对应的组件名一一对应。例如：

```json
{
  "head": {
    "title": "戒子",
    "description": "Author:SimonMa,Category:Personal Blog",
    "favicon": "favicon.ico"
  }
}
```

上述配置会自动应用到 `layout/head.pug` 组件中：

```pug
head
  title #{head.title}
  meta(charset="utf-8")
  meta(name="Description" content=`${head.description}`)
  link(rel="icon" href=`${head.favicon}` type="image/x-icon")
```

## 高级配置

### 1. WebGL 背景

首页默认使用 [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) 作为背景。如需关闭，请在 `config.json` 中设置：

```json
"intro": {
  "background": false
}
```

### 2. 支持作者

默认情况下，项目启用了 `supportAuthor` 选项，支持作者功能包括：

- 首页右上角显示“章鱼猫”图标。
- 控制台打印作者的站点信息。

如需关闭，请在 `config.json` 中设置：

```json
"intro": {
  "supportAuthor": false
}
```

### 3. 图标替换

项目中的图标来自 [阿里巴巴矢量图标库](https://www.iconfont.cn)。替换步骤如下：

1. 选择并添加图标到项目，将颜色调整为白色。
2. 使用 Font Class 方式生成链接。
3. 复制生成的内容。
4. 替换 `css/common/icon.scss` 文件中的内容，保留 `.icon` 选择器。
5. 更新 `config.json` 中 `main.ul.*.icon` 的配置。

## 项目部署

执行以下命令生成项目文件：

```sh
npm run build
```

生成的文件会存放在 `dist` 目录中。你可以将该目录部署到任意服务器托管平台。

### 示例：部署到 GitHub Pages

1. 创建仓库 `你的用户名.github.io`。
2. 在 `dist` 目录中执行以下命令：

	 ```sh
	 cd dist
	 git init
	 git add -A
	 git commit -m "Deploy to GitHub Pages"
	 git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
	 git push -f origin master
	 ```

3. 在 GitHub 仓库设置中启用 GitHub Pages。
4. 访问 `https://你的用户名.github.io` 即可浏览。

## 赞助与支持

开发一个优秀的项目需要大量的时间和精力投入。如果你觉得这个项目对你有帮助，欢迎通过以下方式支持我：

- **Star** 项目
- **赞助** 开发者

感谢你的支持！

## 协议

本项目基于 `LGPL-3.0` 协议开源。

---

通过以上优化，`README.md` 文件更加简洁明了，同时保留了所有关键信息，便于开发者快速上手和理解项目。