# 路由配置
路由配置沿用了vue-cli的配置方案，具体配置参考`vue-router`

路由配置地址
```text
src/renderer/router/index.js
```
配置示例
```javascript
import Layout from '@/vued/layout'
Vue.use(Router)
export default new Router({
    routes: [
        {
            path: '/',
            name: 'HelloWorld',
            component: Layout
        }
    ]
})
```