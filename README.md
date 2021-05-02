# injectFilter.js
注入攻击过滤器(兼容IE)-实现过滤文本或DOM元素中的敏感关键字防止XSS、命令注入、sql注入攻击

大小：4KB

NPM 地址：https://www.npmjs.com/package/xssfilter-js
# Docs文档:
## 安装：
```
npm install xssfilter-js
```
## options 配置项:
```javascript
//创建一个InjectFilter对象，可传入options配置对象
var inf = new InjectFilter(options);


options.tokens = 可添加额外的自定义过滤字符，对象类型键值对
{'需要替换的目标字符':'字符1'} 
key为需要替换的字符，value为想要将目标字符替换成的字符。



options.xss = true; 
默认为true。 需为布尔值，是否启用过滤xss注入


options.command = true;
默认为true。 需为布尔值，是否启用过滤command(命令注入)



options.sql = true;
默认为true。 需为布尔值，是否启用过滤sql注入
注：命令和sql将过滤成对应的‘全角’文本(如ｓｅｌｅｃｔ　、ｄｅｌｅｔｅ　ｆｒｏｍ、ｐｉｎｇ )
```
# Demo：
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="injectFilter.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.5.1/jquery.js"></script>
</head>
<body>
    <div id='aa' onclick="javascript:alert('hello world')">) or 1=1</div>
</body>
<script>
  var inf = new InjectFilter({tokens:{'or':'|||'}});
     $('#aa').html(inf.filter(document.getElementById('aa')))
</script>

</html>
```
ES6:
```javascript
import injectFilter from './injectFilter';
```
