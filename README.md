# 一、代码规范
### 1、DOCTYPE声明
```
<!DOCTYPE html>
```
### 2、页面语言LANG
```
<html lang="zh-CN">
```
### 3、元素及标签闭合
为了能让浏览器更好的解析代码以及能让代码具有更好的可读性，有如下约定：
- 所有具有开始标签和结束标签的元素都要写上起止标签
- 空元素标签都 不 加 “/” 字符。空元素包括：area、base、br、col、command、embed、hr、img、input、keygen、link、meta、param、source、track、wbr
- 通过sublime的Emmet插件的自动完成功能，可以很好地执行以上两条。

# 二、书写风格
### 1、HTML标签名、类名、标签属性和大部分属性值统一用小写
```
<div class="demo" id="demo"></div>
```
### 2、不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含
```
<link rel="stylesheet" href="">
<script src=""></script>
```
### 3、元素属性
- 元素属性值使用双引号语法
- 元素属性值可以写上的都写上
### 4、使用字符实体
以字符实体代替HTML语法相同的字符，避免浏览器解析错误
```
<a href="#">more&gt;&gt;</a>
```
常见实体字符：

字符 | 名称 | 实体名 | 实体数
---|---|---|---
" | 双引 | ```&quot;``` | ```&#34;```
& | &符 | ```&amp;``` | ```&#38;```
< | 左尖括号（小于号） | ```&lt;``` | ```&#60;```
> | 右尖括号（大于号） | ```&gt;``` | ```&#62;```
&nbsp; | 空格 | ```&nbsp;``` | ```&#160;``` 
&nbsp; | 中文全角空格  |  | ```&#12288;``` | 
¥ | 元 | ```&yen;``` | ```&#165;```
© | 版权 | ```&copy;``` | ```&#169;```
® | 注册商标R | ```&reg;``` | ```&#174;```
™ | 商标TM | ```&trade;``` | ```&#8482;```
· | 间隔符 | ```&middot;``` | ```&#183;```
« | 左双尖括号 | ```&laquo;``` | ```&#171;```
» | 右双尖括号 | ```&raquo;``` | ```&#187;```
° | 度 | ```&deg;``` | ```&#176;```
× | 乘 | ```&times;``` | ```&#215;```
÷ | 除 | ```&divide;``` | ```&#247;```
‰ | 千分比 | ```&permil;``` | ```&#8240;```

### 5、<a>标签的href若无跳转url，统一使用javascript:;
```
<a href="javascript:;">我是一个链接</a>
```
### 6、代码缩进
统一使用四个空格进行代码缩进，使得各编辑器表现一致
### 7、标签嵌套
元素嵌套规范，每个标签元素独立一行； 
换行若对样式造成影响除外，如增加一个换行符会在页面产生间距，对样式控制产生影响。必须在代码中注释说明。
```
<div>
    <h1></h1>
    <p></p>
</div>
<!-- tips中的span标签必须写在一行，否则会对样式产生影响 -->
<p class="tips"><span></span><span></span></p>
```
块元素可以包含内联元素和部分块元素，内联元素不能嵌套块元素 
段落元素与标题元素只能嵌套内联元素
```
<h1>
    <span></span>
</h1>
<p>
    <span></span>
    <span></span>
</p>
```
嵌套规则可参考： 
![image](https://raw.githubusercontent.com/wangcapsk/html--standard/master/pic/qt.jpg)
# 三、注释规范
代码注释的价值在于：方便他人调用和维护。  
代码注释是用来解释一段代码的意图而不是行为。
### 1、单行注释
注释方法：注释内容前后各一个空格字符，注释位于要注释代码的上面，单独占一行。 使用场景：  
（1）需要与前端配合，解释如何实现页面交互，如状态切换、模块切换等。  
（2）需要后续维护的开发人员注意的要点，需要简单描述
```
<!-- 选中样式：给li标签添加类on -->
<ul>
    <li class="on"><a href="floor1">楼层1</a></li>
    <li><a href="floor2">楼层2</a></li>
</ul>
```
### 2、模块注释
注释方法：注释内容前后各一个空格字符，<!-- Comment Text[[ --> 表示模块开始，<!-- Comment Text]] --> 表示模块结束，模块与模块之间相隔一行 使用场景：  
（1）页面模块较多，交互复杂时，需要清晰展现页面结构。通过给每个模块添加注释，方便查找与维护。
```
<!-- 吸底导航[[ -->
<!-- 展开给sale-tpl-bottom添加类sale-tpl-bottom-open -->
<section class="sale-tpl-bottom">
    <div class="sale-floor-main">
        <ul class="fn-clear">
            <li><a href="#1F" class="on">定位锚点</a></li>
            <li><a href="#2F">定位锚点</a></li>
        </ul>
    </div>
</section>
<!-- 吸底导航]] -->

<!-- 吸顶导航[[ -->
<!-- 展开给sale-tpl-top添加类sale-tpl-top-open -->
<section class="sale-tpl-top">
    <div class="sale-floor-main">
        <ul class="fn-clear">
            <li><a href="#1F" class="on">定位锚点</a></li>
            <li><a href="#2F">定位锚点</a></li>
        </ul>
    </div>
</section>
<!-- 吸顶导航]] -->
```
### 3、嵌套模块注释
注释方法：结合以上两种注释场景，嵌套模块的注释写在模块结尾标签底部，单独一行。   
使用场景：当模块注释内再出现模块注释的时候，为了突出主要模块
```
<!-- sku列表区[[ -->
<div class="pro-main">
    <div class="sports">
        ...
    </div>
    <!-- /运动楼层 -->

    <div class="watches">
        ...
    </div>
    <!-- /手表楼层 -->
</div>
<!-- sku列表区]] -->
```