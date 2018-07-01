---
title: DOM知识整理
date: 2018-07-01 18:13:24
tags: 
- dom
- javascript
categories:
- javascript
---

其实想写博客已经很久了，平时的一些知识点或者学到主要是记录到有道云里面，都没有系统地整理过。但是发现拖得越久就越难受，还是有时间就写了

### DOM的知识整理

> js

#### 选择器
1.querySelector() //返回匹配的的第一个元素，支持嵌套查找（类似jquery的选择器）
2.querySelectorAll() //返回NodeList对象
3.getElementById() //通过ID查找
4.getElementByTagName() //通过标签名查找
5.getElementByClassName() //通过类名查找
6.getElementByName() //通过name字段查找， 例如Input标签里的name属性

#### 元素遍历
1.childElementCount //返回子元素（不包括注释和文本）个数
2.firstElementChild //指向第一个子元素，类似css里的first-child，js改变样式的firstChild
3.lastElementChid //指向最后一个子元素
4.previousElementSibling //指向前一个同级元素，同previousSibling
5.nextElementSibling //指向后一个同级元素，同nextSibling

#### 类名操作相关
classList:
1. add //添加类
2. remove //移除类
3. contains //判断是否存在某类， 返回布尔值
4. toggle //判断某类的存在与否，在则删除，不在则添加

#### 焦点管理
1. activeElement //判断是否为获得焦点元素，可查找焦点元素
```js
var button = document.getElementById('myButton');
button.focus();
alert(document.activeElement === button);  //true
```

2. hasFocus('xxxx') 判断页面文档是否获得了焦点
```js
var button = document.getElementById('myButton');
button.focus();
alert(document.hasFocus())
```

#### 文档变化
1. readyState属性，描述文档的加载状态
    1. loading，正在加载文档
    2. interactive， 文档加载完成，但是图像等其他资源仍在加载
    3. complete， 已经加载完文档

2. compatMode渲染模式检验
    1. CSS1Compat: 标准模式
    2. BackCompat: 混杂模式

3. head属性，可修改head标签信息，可使用则用， 否则用查找方法
```js
var head = document.head || document.getElementByTagName('head')[0];
```

#### charset，字符集修改
```js
document.charset //utf-8
```

#### data-自定义属性，通过dataset获取或者修改自定义属性
```js
<div id="my" data-appId="123" data-name="test"></div>
var div = document.getElementById('my');
var appId = div.dataset.appId; //123
var name = div.dataset.namel //test

```
