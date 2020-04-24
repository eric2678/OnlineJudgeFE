# OnlineJudge Front End
[![vue](https://img.shields.io/badge/vue-2.5.13-blue.svg?style=flat-square)](https://github.com/vuejs/vue)
[![vuex](https://img.shields.io/badge/vuex-3.0.1-blue.svg?style=flat-square)](https://vuex.vuejs.org/)
[![echarts](https://img.shields.io/badge/echarts-3.8.3-blue.svg?style=flat-square)](https://github.com/ecomfe/echarts)
[![iview](https://img.shields.io/badge/iview-2.8.0-blue.svg?style=flat-square)](https://github.com/iview/iview)
[![element-ui](https://img.shields.io/badge/element-2.0.9-blue.svg?style=flat-square)](https://github.com/ElemeFE/element)
[![Build Status](https://travis-ci.org/QingdaoU/OnlineJudgeFE.svg?branch=master)](https://travis-ci.org/QingdaoU/OnlineJudgeFE)

>### A multiple pages app built for OnlineJudge. [Demo](https://qduoj.com)



1. 部署環境準備
  node.js環境安裝和配置，我的伺服器作業系統是Ubuntu18.04，ubuntu安裝軟體很簡單，通常sudo apt-get install 安裝包名稱即可達到安裝的目的。但是node.js預設通過這種安裝版本會不符合官方文件上面要求的那樣。所以建議最好還是不要通過這種形式安裝。

  node.js下載地址:https://nodejs.org/dist/

  可以選擇對應的版本，最好是高於8.12.0或者等於8.12.0。

  我是通過原始碼(已經編譯好了)安裝，步驟如下:
  
  ```bash
  wget https://nodejs.org/dist/v8.12.0/node-v8.12.0-linux-x64.tar.xz
  tar -xvf node-v8.12.0-linux-x64.tar.xz
  sudo mv node-v8.12.0-linux-x64 /usr/local
  sudo ln -s /usr/local/node-v8.12.0-linux-x64/bin/node /usr/local/bin/node 
  sudo ln -s /usr/local/node-v8.12.0-linux-x64/bin/npm /usr/local/bin/npm
  ```

2. 部署
  步驟如下:
  
  ```bash
  git clone https://github.com/QingdaoU/OnlineJudgeFE.git
  cd OnlineJudgeFE
  npm install
  ```
  https://github.com/nodejs-tw/nodejs-wiki-book/blob/master/zh-tw/node_npm.rst
  
  如果出現以下代碼:
  
  ```
  npm WARN notice [SECURITY] mime has the following vulnerability: 1 moderate. Go here for more details: https://www.npmjs.com/advisories?search=mime&version=1.3.6 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] jquery has the following vulnerability: 1 moderate. Go here for more details: https://www.npmjs.com/advisories?search=jquery&version=3.1.1 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] js-yaml has the following vulnerabilities: 1 high, 1 moderate. Go here for more details: https://www.npmjs.com/advisories?search=js-yaml&version=3.7.0 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] set-value has the following vulnerability: 1 high. Go here for more details: https://www.npmjs.com/advisories?search=set-value&version=2.0.0 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] mixin-deep has the following vulnerability: 1 high. Go here for more details: https://www.npmjs.com/advisories?search=mixin-deep&version=1.3.1 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] marked has the following vulnerability: 1 moderate. Go here for more details: https://www.npmjs.com/advisories?search=marked&version=0.3.19 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.
  npm WARN notice [SECURITY] jquery has the following vulnerabilities: 1 high, 1 moderate. Go here for more details: https://www.npmjs.com/advisories?search=jquery&version=2.2.4 - Run `npm i npm@latest -g` to upgrade your npm version, and then `npm audit` to get more info.

  > uglifyjs-webpack-plugin@0.4.6 postinstall /home/fcu/OnlineJudgeFE/node_modules/webpack/node_modules/uglifyjs-webpack-plugin
  > node lib/post_install.js

  npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules/fsevents):
  npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

  added 1440 packages in 32.112s
  ```
  
  執行:
  
  ```bash
  npm i npm@latest -g
  npm audit
  ```
  
  如果出現:
  
  ```bash
  found 859 vulnerabilities (312 low, 34 moderate, 513 high) in 15761 scanned packages
  run `npm audit fix` to fix 825 of them.
  8 vulnerabilities require semver-major dependency updates.
  26 vulnerabilities require manual review. See the full report for details.
  ```
  
   執行:
  
  ```bash
  npm audit fix
  ```
  
  ```
  fixed 825 of 859 vulnerabilities in 15761 scanned packages
  26 vulnerabilities required manual review and could not be updated
  6 package updates for 8 vulnerabilities involved breaking changes
  (use `npm audit fix --force` to install breaking changes; or refer to `npm audit` for steps to fix these manually)

  ```
  
  ```bash
  NODE_ENV=development npm run build:dll
  export TARGET=https://qduoj.com/
  #target指的是後臺代理伺服器地址，通常為judgeserver
  npm run dev
  ```











## Features

+ Webpack3 multiple pages with bundle size optimization
+ Easy use simditor & Nice codemirror editor
+ Amazing charting and visualization(echarts)
+ User-friendly operation
+ Quite beautiful：)

## Get Started

Install nodejs **v8.12.0** first.

```bash
npm install
# we use webpack DllReference to decrease the build time,
# this command only needs execute once unless you upgrade the package in build/webpack.dll.conf.js
NODE_ENV=development npm run build:dll

# the dev-server will set proxy table to your backend
export TARGET=http://Your-backend

# serve with hot reload at localhost:8080
npm run dev
```

## Screenshots

[Check here.](https://github.com/QingdaoU/OnlineJudge)

## Browser Support

Modern browsers and Internet Explorer 10+.

## LICENSE

[MIT](http://opensource.org/licenses/MIT)
