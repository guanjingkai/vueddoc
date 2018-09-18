# 网络请求
调用示例
```javascript
this.http("get", "apiName", {}, function(data) {

});
```
|参数|解释|
|--------|--------|
|请求类型|可选 `get` `post`|
|接口名称|直接传递 `/xxx` 即可，系统会根据配置自动添加协议 和 `baseUrl`|
|请求参数|json格式的请求参数，ajax的body|
|回调方法|请求成功后，API返回的主数据部分(即配置中的`dataName`)，非API原有格式|