# f2e-coding-standards
***
## 1. CSS/less
***
### 1.1 代码组织
公用的代码抽取出来放到```/lib```文件夹下。

    less/lib/reset.less
    less/modA.less
    less/modB.less
### 1.2 命名规范
给CSS用的类或者id命名为用```-```分隔的小写字母，如

    <div class="category-nav" id="category-nav"></div>
给js用的类或者id命名为用```J_```开头用```_```连接的小写字母，如

    <a class="J_submit_btn">提交</a>

### 1.3 格式化书写
冒号后面加空格，分号不可省略。

    .selector { 
        property: value;
        property: value; 
    }
多个选择器用逗号空格加换行隔开。

    .selector1, 
    .selector2, 
    .selector3 {}
单行css应该用tab(4个空格)区分不同层次的样式，且不应该超过5层。

    .pop-sty{  }
        .pop-sty .content{ }
            .pop-sty .content .pop-hd{ }
            .pop-sty .content .pop-bd{ }
兼容多个浏览器时，将标准规则声明写在后面。

    -webkit-border-radius: 4px;
       -moz-border-radius: 4px;
            border-radius: 4px;
    
### 1.4 选择器
避免使用```*```选择器。

避免使用低效的选择器，如：

    ul > li > a { }
    #footer > h3 { }
    ul#top_blue_nav { }
    #searbar span.submit a { }
    .target #target-node { }
使用类选择器或者id选择器时不要再加标签名，如：

    div#nav-header {}
### 1.5 其他注意点
避免使用```!important```声明。

不要使用```@import```。

避免修改标签样式

    div {}
避免写内联的style

    <div style=""></div>
padding和margin如果有多个尽量合并成一个。

0后面的单位省略掉。
    
## 2. js
### 2.1 命名规范
一般变量名为小写字母驼峰式```dishList```
构造器首字母大写
    
    function Person() {}
私有变量下划线开头```_index```

常量名全部大写，单词间用下划线分隔```DEAFULT_ERROR_MSG```

布尔值推荐用```is, has, can, flag```

循环体中的整数一般命名为```i, j, k, m, n```
### 2.2 代码格式
四空格缩进。

语句要以分号结尾。

变量声明放在函数最上面。

    function getQuery() {
        var query = {};
    }
数组成员间的逗号后面接空格。
    
用来包含语句的括号对后面接空格，赋值及比较符号两边需要空格。
    
    for (var i = 0; i < l; i++) { 
        
    } 
### 2.3 最佳实践
使用单引号。

频繁读取的dom先存起来。

    var dishBoxList = $('.J_dish_box');
避免使用```with, void, eval```

下面类型的对象不建议用new构造：

    new Number
    new String
    new Boolean
    new Object // 用{}代替
    new Array // 用[]代替
    
引用对象成员用```obj.prop1```代替```obj['prop1']```，除非属性名是变量。

for-in循环体中必须用```hasOwnProperty```方法检查成员是否为自身成员，避免来自原型链上的污染。

使用严格的条件判断符。

用逻辑运算符和三元运算符代替条件判断语句。

函数接受的参数不要超过3个。

函数不要超过100行。
