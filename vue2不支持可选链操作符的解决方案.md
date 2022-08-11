## 在非<template/>中使用可选链操作符
```
// 在babel.config.js中添加如下插件：
plugins: [
  "@babel/plugin-proposal-optional-chaining"
]
```

## 在<template/>中使用可选链操作符
```
// 引入如下解析函数
Vue.prototype.$$ = (target, key) => {
  const keys = key.split('?.')
  return keys.reduce((a, b) => a?.[b], target);
}
// 使用
<template>
  <div>{{ $$(obj, 'a?.b?.c') }}</div>
</template>
```
