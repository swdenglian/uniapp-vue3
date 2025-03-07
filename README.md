# uni-pro

## 支持
- [x] Android离线打包/命令打包
- [x] Pinia
- [x] uni-ui
- [x] Axios

## Pro路由说明

本项目采用约定式路由，按照下方规则生成路由，即生成uni-app的[pages.json](https://uniapp.dcloud.net.cn/collocation/pages.html):

- 监听 src/ui/pages 目录，其中index.vue将会生成对应的路由，其余的均不生成路由
- 更新 pages.json 时机
  - 创建 index.vue 文件时
  - 删除 index.vue 文件时
  - 项目启动时

## Pro内置工具说明
- [本地缓存](./docs/Storage.md)
- [Http请求](./docs/HttpClient.md)
- [弹窗提示](./docs/Message.md)
- [导航API](./docs/Navigate.md)
- Pro项目内置组件
  - [Page 页面组件](./src/ui/components/Page/README.md)
  - [NavBar 导航栏组件](./src/ui/components/NavBar/README.md)
  - [Pagination 分页组件](./src/ui/components/Pagination/README.md)

## Pro命令说明
```json5
{
  "scripts": {
    // 构建不同环境的Android包，构建结果在android/app/build/outputs/apk/release/ 下
    "build:android:prod": "cross-env ENV=.env.prod vite-node ./scripts/build-android.ts",
    "build:android:dev": "cross-env ENV=.env.dev vite-node ./scripts/build-android.ts",
    "build:android:test": "cross-env ENV=.env.test vite-node ./scripts/build-android.ts"
  }
}
```

## src/manifest.json 说明

```json5
{
  "name": "uni-app-demo", // 项目名称
  "appName": "uni-Android离线样例", // android app 中文名称用于显示在桌面上
  "appid": "__UNI__16FC452", // uni-app 的 appid
  "description": "用于uni-app脚手架,支持android构建", // 项目描述
  "versionName": "1.0.0",
  "versionCode": 1,
  "transformPx": false,
  "android": {
    "dcloudAppKey": "05ccb5d7963e42b6872ae9de2e675bd2", // 必填, 可在开发者后台查看 https://dev.dcloud.net.cn/, 应用管理-->我的应用-->应用信息-->各平台信息-->Android App-->查看离线key
    "applicationId": "com.wwxan.uniapp.demo", // Android App 包名
    "signingConfigs": { // android 签名信息
      "storeFile": "android.keystore", // 签名文件路径
      "keyPassword": "skzi44SU", // 签名文件密码
      "storePassword": "skzi44SU" // 签名文件密码
    }
  }
}
```

## 技术栈
- [vite](https://cn.vitejs.dev/guide/)
- [typescript](https://www.typescriptlang.org/)
- [Pinia](https://pinia.vuejs.org/zh/)
- [Axios](https://axios-http.com/docs/intro)
- [uni-app](https://uniapp.dcloud.net.cn/)
  - [uni-ui](https://uniapp.dcloud.net.cn/component/uniui/uni-ui.html)
  - [android离线打包](https://nativesupport.dcloud.net.cn/AppDocs/usesdk/android.html)
