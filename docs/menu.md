# 菜单配置
### mapper路由映射
>存在价值 用于保存路由-路由名称 的关联关系，简化菜单配置，并支持tab页显示页面名称

mapper配置地址
```text
src/renderer/router/mapper.js
```
配置示例
```javascript
export default {
    mmDashboard: {
        key: "mmDashboard",
        title: "主控台",
        path: "/service/dashboard"
    }
}
```

|字段|描述|
|--------|--------|
|json 一级 key |采用json格式是方便获取配置，json的一级 key 和 二级 key的value`保持一致`|
|key|路由的key|
|title|路由的中文名称|
|path|路由|

### 菜单配置
系统菜单配置本身支持 多个独立菜单配置，用于在不同模块中展示不同菜单，目前该功能屏蔽。
一级节点统一成`merchant`
配置文件参考
```javascript
import mainMenuConfig from "./mapper.js";
export default {
    merchant: {
        paIndex: {
            key: "paIndex",
            title: "主页",
            childmenu: {
                paIndex: mainMenuConfig["paIndex"]
            }
        }
    }
}
```
>系统目前只支持二级菜单，其中一级菜单不对应页面(`无路由`)，所以一级页面的key 和 title直接在`menu.js`的配置文件中配置，二级菜单配置通过`mapper.js`来读取配置

`childmenu` 的子菜单的`key` 最好和 `mapper.js` 中json `一级key` 保持一致