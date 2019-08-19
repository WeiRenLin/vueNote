# Vue Resource

## 以 非同步的方式去後端拿取資料然後在網頁端上呈現

## 1. 優點

* 支援 Promise\(非同步\)
* 支援 URI Template \(路由的概念\)
* 支援 Firefox、Chrome、Safari、Opera、以及IE9+

## 2. 安裝

```javascript
$ npm install vue-resource --save
or
$ bower install vue-resource --save
```

## 3. 使用方式

### a. 首先新增名為resource的資料夾並在裡面新增一個resource.js的檔案

### b. 接著在裡面輸入以下的範例碼，即完成設定

```javascript
import Vue from 'vue'
//後端api位址
var domain = 'https://localhost:8080/api'
export const resourceVM = Vue.resource(domain + '/ResourceVM{/id}');
```

### 

