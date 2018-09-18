# 快速开始
从github获取最新的项目代码
```shall
git clone gitlab私服地址
```
然后进入项目根目录
```shall
cd projectName
```
安装依赖并运行项目
```shall
npm install
npm run dev
```
打包
```shall
npm run build
npm run build:web
```
>build 打包生成 exe dmg 文件

>build:web 打包生成 网页

目录结构
```shall
-| build/
-| dist/ 
  -| electron/ win mac 打包结果
  -| web/ web打包结果
-| src/
  -| main/
  -| renderer/
    -| components/
    -| config/ vued的配置文件
    -| mock/ mock数据
    -| router/ vue路由
    -| store/ vuex
    -| vued/
      -| core/ vued核心
      -| display/ vued展示型组件
-| static/
```