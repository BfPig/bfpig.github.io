---
title: HTML 使用规范
date: 2017-8-13 20:46:25
---

## 通用架构
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title>极客学院IT在线教育平台-中国专业的IT职业在线教育平台</title>
    <meta name="keywords" content="极客学院,IT职业教育,IT在线教育平台,IT在线教育,IT在线学习,it职业培训,android,ios,flash,java,python,html5,swift,cocos2dx" />
    <meta name="description" content="极客学院作为中国专业IT职业在线教育平台,拥有海量高清IT职业课程,涵盖30+个技术领域,如Android,iOS ,Flash,Java,Python,HTML5,Swift,Cocos2dx等视频教程.根据IT在线学习特点,极客学院推出IT学习知识体系图,IT职业学习实战路径图,帮助IT学习者从零基础起步,结合IT实战案例演练,系统学习,助你快速成为IT优秀技术人才！" />
</head>
<body>

</body>
</html>
```

## 注意事项

### 标签属性书写顺序
class 用于标识高度可复用组件，因此应该排在首位。id 用于标识具体组件，一般提供给JS使用。
1. class
2. id, name
3. data-*
4. src, for, type, href
5. title, alt

### 语法
1. 用4个空格来代替制表符（tab）
2. 嵌套元素应当缩进一次
3. 对于属性的定义，确保全部使用双引号，不要使用单引号。

### 避免冗余
尽量遵循 HTML 标准和语义，但是不要以牺牲实用性为代价。任何时候都要尽量使用最少的标签并保持最小的复杂度。（尤其勿滥用div标签）
```html
  <!-- 不规范的写法 -->
  <span class="avatar">
      <img src="...">
  </span>

  <!-- 规范的写法 -->
  <img class="avatar" src="...">
```

### 错误嵌套
1. a标签不可以嵌套交互式元素
2. 块级元素可以包含内联元素和某些块级元素，内联元素不能包含块级元素，只能包含内联元素
3. p标签不能包含块级元素
4. 这些标签不可包含块级元素
5. li标签可以包含div以及ul，ul的子元素应该只有li
6. 元素并排（块级和块级并列，内联和内联并列)

#### 语法错误
浏览器是不能够正常解析的,有的虽然解析正常，但却达不到预想的目的
#####  a标签不可以嵌套交互式元素
a标签不可以嵌套交互式元素[a， audio（如果设置了controls属性）， button， details， embed， iframe， img（如果设置了usemap属性）， input（如果type属性不为hidden状态）， keygen， label， menu（如果type属性为toolbar状态），object（如果设置了usemap属性）， select， textarea， video（如果设置了controls属性）]
```html
/*下面这些写法浏览器是不能够正常解析的,有的虽然解析正常，但却达不到预想的目的*/
<a href="">
    <a href="">click</a>
</a>
<a href="">
    <button>click</button>
</a>
<a href="">
    <input type="text">
</a>
<a href="">
    <textarea name="" id="" cols="10" rows="5"></textarea>
</a>
```

#### 语义错误
页面可能正常解析，但不符合语义。这是因为浏览器自带容错机制，对于不规范的写法也能够正确的解析，各浏览器的容错机制不同，所以尽量按规范来写。

##### 块级元素可以包含内联元素和某些块级元素，内联元素不能包含块级元素，只能包含内联元素
```html
/*规范的写法*/
<div>
    <h2>jikexueyuan</h2>
    <p>IT education</p>
</div>

/*不规范的写法*/
<span>
    <div>wrong</div>
</span>
```

#####  h1、h2、h3、h4、h5、h6、p 标签不能包含块级元素
```html
/*不规范的写法*/
<p>
    <h1></h1>
</p>
<p>
    <div></div>
</p>

/*不规范的写法*/
<h1>
    <h2></h2>
</h1>
<h2>
    <p></p>
</h2>
```

##### li标签可以包含div以及ul
```html
/*规范的写法*/
<li>
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>
    <div></div>
</li>

/*不规范的写法*/
<ul>
    <a href="">迷路的a标签</a>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

##### 元素并排（块级和块级并列，内联和内联并列)
```html
/*规范的写法*/
<div>
    <h2></h2>
    <p></p>
</div>
<div>
    <img src="" alt="">
    <a href=""></a>
    <span></span>
</div>

/*不规范的写法*/
<div>
    <span>我是内联元素</span>
    <p>我是块级元素</p>
</div>
```
