# cesium-vue-static(基于vuecli2.x)

> 一个整合了Cesium的VueCli2.x的脚手架工具[静态资源版]

1.项目为VueCli+Cesium静态资源版, 集成了cesium罗盘插件与cesium量算插件。

2.根据您的项目需要，可以配置自己需要的模块，如Ui模块(ElementUi,museUi)等。

3.建议开发者将写好的Cesium功能封装成一个独立的模块，而不是将cesium的属性赋值给Vue的data对象中(会造成一些性能问题)。 

为什么使用静态资源版？
优点：一些第三方cesium插件并没有提供NPM包,以模块化的方式引入cesium没办法直接使用这些第三方插件包,通过静态资源的方式可以解决此问题。
缺点：没办法以模块的方式引入cesium,也就意味着无法按需加载。 

静态资源版在开发方式有何不同？
在开发方法上并没有与模块化版本(cesium-vue)没有其他区别,语法与cesium的使用方式一致,包括打包方式。

## Build Setup

``` bash
# 安装依赖
npm install

# 运行开发环境
npm run dev

# 编译
npm run build

# 编译分析报告
npm run build --report

# 打开浏览器查看运行结果
localhost:8080
```

# 浏览器兼容报告
![Image text](https://raw.githubusercontent.com/ShareQiu1994/img-folder/master/webGL.png) 
