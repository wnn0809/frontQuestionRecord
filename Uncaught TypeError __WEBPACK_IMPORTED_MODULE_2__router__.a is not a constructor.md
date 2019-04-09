## 1.问题描述

- 使用webpack构建Vue单页面应用项目，项目运行时，浏览器报“Uncaught TypeError: __WEBPACK_IMPORTED_MODULE_2__router__.a is not a constructor”，组件中的内容也不能正常显示，` <router-link :to="{path:'animal'}">to animal</router-link>`也不能正常出现`<a>`标签的效果。页面时空白的。
	
## 2.解决思路与方法
- 分析
VueRouter的引入不能使用npm安装时自带的

	```javascript
	import VRouter from './router'
	```
	因为./表示当前src目录，目录下并没有router文件，所以webpack会找不到，所以会报错。
- 解决
将`import VRouter from './router'`改为

	```javascript
	import VRouter from 'vue-router'
	```
	修改之后，npm运行项目正常。
	
	
详细参考我的个人博客，一些代码图片在博客上，博客地址为： https://blog.csdn.net/w1418899532/article/details/89099441