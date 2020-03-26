###
# postcss-px2rpx-transform 

[PostCSS](https://github.com/ai/postcss) 单位转换插件，目前已支持小程序端（px 转rpx），H5 端（px 转 rem）及 RN 端。

基于 [postcss-pxtransform](https://github.com/NervJS/taro/tree/2.x/packages/postcss-pxtransform)。

## Install

```shell
$ npm install postcss-px2rpx-transform --save-dev
```

## Usage

```javascript
# postcss.config.js

module.exports = {
  parser: require("postcss-comment"),
  plugins: [
    require("postcss-px2rpx-transform")({
      platform: "weapp",
      designWidth: 375
    }),
  ]
};

```

### 小程序
```js
options = {
    platform: 'weapp',
    designWidth: 750,
}
```

### H5
```js
options = {
    platform: 'h5',
    designWidth: 750,
}
```

### RN
```js
options = {
    platform: 'rn',
    designWidth: 750,
}
```

### 输入/输出

默认配置下，所有的 px 都会被转换。

```css
/* input */
h1 {
    margin: 0 0 20px;
    font-size: 32px;
    line-height: 1.2;
    letter-spacing: 1px;
}

/* weapp output */
h1 {
    margin: 0 0 20rpx;
    font-size: 32rpx;
    line-height: 1.2;
    letter-spacing: 1rpx;
}

/* h5 output */
h1 {
    margin: 0 0 0.5rem;
    font-size: 1rem;
    line-height: 1.2;
    letter-spacing: 0.025rem;
}

/* rn output */
h1 {
    margin: 0 0 10px;
    font-size: 16px;
    line-height: 1.2;
    letter-spacing: 0.5px;
}

```

