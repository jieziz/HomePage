# Jez - HomePage

[中文版说明](README.zh_CN.md)

## Introduction

`Jez` is a sleek and modern personal homepage project. It features a dynamic WebGL background, responsive design, and a lightweight yet powerful tech stack. Whether you're looking to create your own homepage or explore modern web development techniques, this project is a great starting point.

[Online Demo](http://jesz.org)

## Prerequisites

Before you begin, ensure your development environment meets the following requirements:

- **Node.js**: Version 6.0 or higher
- **Git**: Installed and available on your system

## Installation

Follow these steps to set up the project:

```sh
# Clone the repository
git clone https://github.com/jieziz/HomePage.git

# Navigate to the project directory
cd HomePage

# Install dependencies
npm install

# Start the development server
npm run dev
```

## Troubleshooting

If you encounter issues during installation, try the following steps:

```sh
# 1. Install cnpm (Taobao NPM mirror for faster installation in China)
npm install -g cnpm --registry=https://registry.npm.taobao.org

# 2. Remove node-sass and gulp-sass from package.json
cnpm install node-sass --save-dev
cnpm install gulp-sass --save-dev

# 3. Install remaining dependencies
cnpm install

# 4. Install Sass
cnpm install sass --save-dev
```

## Features

`Jez` offers a range of impressive features:

1. **Highly Encapsulated**: All page information is neatly organized for easy maintenance and scalability.
2. **WebGL Background**: Uses [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) for a dynamic and visually stunning background.
3. **SCSS Preprocessor**: Write clean and modular CSS with SCSS.
4. **Pug Template Engine**: Simplify HTML development with Pug.
5. **Gulp Build Tool**: Preconfigured build scripts for streamlined development.
6. **Smooth Animations**: Enjoy a seamless and visually appealing user experience.
7. **Responsive Design**: Fully optimized for mobile and desktop devices.
8. **Lightweight**: Total size of referenced CSS and JS files is less than 18.5 KB.
9. **Delayed Page Switching**: Enhanced user experience with delayed event handling.
10. **More to Explore**: Discover additional features as you dive deeper into the project.

## Project Structure

The project is logically divided into two main sections:

1. **`intro`**: The first screen (landing page).
2. **`main`**: The secondary screen (main content).

Functions, styles, and configurations are organized accordingly.

## Basic Configuration

The `config.json` file contains configuration options that map directly to components. For example:

```json
{
  "head": {
    "title": "Jez",
    "description": "Author:SimonMa,Category:Personal Blog",
    "favicon": "favicon.ico"
  }
}
```

This configuration is automatically applied to the `layout/head.pug` component:

```pug
head
  title #{head.title}
  meta(charset="utf-8")
  meta(name="Description" content=`${head.description}`)
  link(rel="icon" href=`${head.favicon}` type="image/x-icon")
```

## Advanced Configuration

### 1. WebGL Background

The homepage uses [WebGL-Fluid-Simulation](https://github.com/PavelDoGreat/WebGL-Fluid-Simulation/) as its background. To disable it, set the following in `config.json`:

```json
"intro": {
  "background": false
}
```

### 2. Support Author

By default, the `supportAuthor` option is enabled, which includes:

- Displaying an "Octopus Cat" icon in the top-right corner of the homepage.
- Printing the author's site information in the console.

To disable this feature, set:

```json
"intro": {
  "supportAuthor": false
}
```

### 3. Icon Replacement

All icons in the project are sourced from [阿里巴巴矢量图标库](https://www.iconfont.cn). To replace them:

1. Select your desired icons, add them to your project, and set their color to white.
2. Use the **Font Class** method to generate the icon library.
3. Copy the generated content.
4. Replace the content in the file `/src/css/common/icon.scss`, ensuring the `.icon` selector remains intact.
5. Update the corresponding configuration in `config.json` under `main.ul.*.icon`.

## Deployment

To build the project for deployment:

```sh
npm run build
```

The output files will be generated in the `dist` directory. You can then deploy this directory to your preferred hosting provider.

### Example: Deploying to GitHub Pages

1. Create a repository named `username.github.io`.
2. In the `dist` directory, run:

	 ```sh
	 cd dist
	 git init
	 git add -A
	 git commit -m "Deploy to GitHub Pages"
	 git remote add origin https://github.com/username/username.github.io.git
	 git push -f origin master
	 ```

3. Enable GitHub Pages in the repository settings.
4. Visit `https://username.github.io` to view your homepage.

If you already have content in your `username.github.io` repository, you can create a new repository (e.g., `blog`) and deploy this project there. This will create a subdirectory at `username.github.io/blog`.

## Sponsor

Developing this project required significant time and effort. If it has been helpful to you, please consider supporting me by:

- **Starring** the repository
- **Sponsoring** the project

Thank you for your support!

## License

This project is licensed under the **LGPL-3.0** license.

---

This optimized version improves readability, removes redundancy, and ensures the content is concise and easy to follow for both new and experienced developers.