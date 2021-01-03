# injectFilter.js
注入攻击过滤器-实现过滤文本或DOM元素中的敏感关键字防止XSS、命令注入、sql注入攻击


#Docs文档
options 配置项
options.tokens = {}; 用户添加额外的过滤字符，对象类型键值对
{'需要替换的目标字符':'字符1'}  key为需要替换的字符，value为想要将目标字符替换成的字符。

options.xss = true; 默认为true。 需为布尔值，是否启用过滤xss注入
options.command = true;默认为true。 需为布尔值，是否启用过滤command(命令注入)
options.sql = true;默认为true。 需为布尔值，是否启用过滤sql注入
