# 全局配置
### vuedConfig
src/config/vuedConfig.js 是 vued框架的全局配置文件

目前文件内容如下
```javascript
export default {
    http: {
        httpType: "http://",//http请求协议
        serverUrl: "api.meituan.com/",//baseUrl
        httpTimeout: 3000,//请求超时时间
        httpResponseEncoding: "utf-8",
        successCode: 200,//正常状态code
        loginTimeOutCode: 201,//登录超时token
        codeName: "code",//接口返回状态码
        msgName: "msg",//接口返回状态描述
        dataName: "data",//接口返回data的字段
    }
}
```
>具体字段看备注了，不做详细说明

### 登录态处理
登录态使用token保存，在每次http请求时，会在head中带有token

结合router的钩子，完成前端的登录权限的控制
```javascript
router.beforeEach((to, from, next) => {
  console.log(localStorage.getItem('token'));
  console.log(to.path);
  if (to.path === '/login') { // 当路由为login时就直接下一步操作
    next();
  } else { // 否则就需要判断
    if (localStorage.getItem('token') != '' && localStorage.getItem('token') != null) { // 如果有用户名就进行下一步操作
      next()
    } else {
      next({ path: '/login' }) // 没有用户名就跳转到login页面
    }
  }
})
```
权限待添加

### 打开页面
通过mapper.js中定义的组件路由映射关系，使用mapper中的key 直接打开一个新的tab页面，展示其对应的组件

调用示例
```javascript
this.openComponent(mapperKey)
```
### 关闭页面
通过pageId 关闭当前tab页面，目前pageId即为tab页面对应的path

调用示例
```javascript
this.closePage(path)
```
