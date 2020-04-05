# Translator

本練習作品基於 Vue.js (vue-cli 2) 與 Yandex Translate API 製作而成

使用前需前往 https://tech.yandex.com/translate/ 申請 API KEY，<br>並將其設定於 config/prod.env.js 的 YANDEX_TRANSLATE_API_KEY 變數

目前該作品只提供翻譯 英文、 韓文、 日文、 簡體中文，<br>可參考 [Yandex Translate API 官方文件](https://tech.yandex.com/translate/doc/dg/concepts/api-overview-docpage/)，於 src/translate_config.js 中自行新增

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
