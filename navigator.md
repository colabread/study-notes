# location object
+ 提供了当前文档的url信息，以及导航功能
+ URLSearchParams API可以用来操作query字符串
## 三种等价的修改location的方式：
+ location.assign(url: string);
+ location.href = url: string;
+ window.location = url: string;
```
以上三种方式都会重载页面并且在浏览器历史记录中留下一条记录
```
```
location.replace(url: string); // 方法不会增加历史记录，而是替换当前url
location.reload(); // 重载页面，可能从缓存加载
location.reload(true);  // 重载页面，从服务器加载
```
```
以下属性被修改后会改变url：
hash | search | hostname | pathname | port
除了hash外，其他属性被修改后会导致页面重载
```
# history object
+ history对象就是用来操作浏览器历史记录的API
```
// 在历史记录中沿着任何方向导航
// 0：重载页面，正数：向前导航，负数：向后导航
history.go(step: number);
history.go(0);  // 重载页面，等价于location.reload()
history.forward();  // 前进一页，等价于history.go(1)
history.back(); // 后退一页，等价于history.go(-1)
history.length; // 历史记录条数
// 以上API不会生成新的历史记录
```
# state management
+ 用户的每次点击都重载页面的时代早已过去
+ 现代web应用通过状态管理来实现在不重载页面的情况下切换页面内容
## hash state management
```
window.addEventListener('hashchange', ({ newURL, oldURL }) => { // TODO });
location.hash = hash: string;
```
## history state management
```
// 当触发history.go(负数)或history.back()时触发回调
window.addEventListener('popstate', ({ state }) => { // TODO });
// 当传入url时会向历史记录中新增一条记录
history.pushState(state: object, title: string[, url: string]);
// 覆盖当前state
history.replaceState(state: object, title: string);
```