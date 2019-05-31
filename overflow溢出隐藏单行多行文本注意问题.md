文章首先更新与[博客](https://blog.csdn.net/w1418899532/article/details/90721147)

## <font color="red">1.单行文本溢出
单行文本隐藏样式使溢出部分使用省略号显示，需要下面3个属性同时设置：

```css
overflow: hidden;
white-space: nowrap;
text-overflow: ellipsis;
```
完整代码如下：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title> overflow 溢出不隐藏 test </title>
    <style type="text/css">
        p {
            overflow:hidden;
            width:180px;
            /*重点是white-space:nowrap;强制不换行这个属性，单行文本的使用*/
            white-space:nowrap;
            border: 1px solid red;
            height: 45px;
            text-overflow: ellipsis;
        }
    </style>
</head>
<body>
    <!-- 兼容火狐和谷歌浏览器 -->
    <p>商品1商品2商品3商品4商品5商品6商品7商品8商品9商品10商品11</p>
    <p>商品1商品2商品3商品4商品5商品6商品7商品8商品9商品10商品11</p>
    <p>商品1商品2商品3商品4商品5商品6商品7商品8商品9商品10商品11</p>
    <p>商品1商品2商品3商品4商品5商品6商品7商品8商品9商品10商品11</p>
</body>
</html>
```

单行文本隐藏谷歌浏览器和谷歌浏览器都可以生效。效果如下：

![效果图](https://img-blog.csdnimg.cn/2019053118512656.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3cxNDE4ODk5NTMy,size_16,color_FFFFFF,t_70)
## <font color="red">2.多行文本溢出

对于多行文字溢出，上面打代码就不试用了，这时使用webkit的私有属性-webkit-line-clamp就只能在谷歌浏览器起作用，在火狐就不起作用了，如下效果：

![多行溢出效果](https://img-blog.csdnimg.cn/20190531190115611.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3cxNDE4ODk5NTMy,size_16,color_FFFFFF,t_70)


