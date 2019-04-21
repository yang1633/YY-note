HTML

## 什么是html

Hyper text markup language

标记 标签  盒子 容器

目标：写页面

html：承载的是内容

学习链接：http://layout.hnz.kim/?file=%E9%A6%96%E9%AI%B5

# 快捷键

ctrl+/   <!--  -->

标签名后按tab    自动补全标签名

标签名*个数 然后按tab     

ctrl+shift+I  引入图片

ctrl+D  复制光标这一行

ul*3>li*3  然后tab  (类似的一样)

ctrl+shitf+/    注释一段

ctrl+/   注释一段 但每一行都有一个注释符号

标签名{$$}然后tab     

.类名*个数 然后tab

ctrl+alt+l  代码自动对齐

!然后tab  在新建file里面自动生成一些模板

ctrl+r  搜索想要的代码

# 标签

标题名，属性，内容

## 标签分类

单标签  双标签

编辑时候的样式和浏览器的样式没有必然联系

## 注释标签

`<!--  -->`

## 标题标签

双标签  h1-h6

## 文字标签

b  strong 加粗

i  em  adress   斜体

s  del    删除

p   span  pre  段落

br  换行

hr  水平线

## 图片标签

`<img/>`

src  路径   绝对路径   相对路径 （./  ../  /）

alt  出错提醒

title  鼠标滑到图片显示标注

## 列表标签

注：

list-style-image:url()   可以改变列表原来默认的符号标记

list-style-position:inside/outside(默认)   符号放在文本内（外）

list-style-type:none/disc/circle/square   设置符号预选样式

list-style:list-style-image:url() list-style-position list-style-type   简写（若自选符号没引进来，则显示后面的预选样式）

无序列表

`<ul> <li></li> </ul>`

有序列表

`<ol> <li></li> </ol>`

自定义列表

`<dl> <dt> <dd></dd> </dt> </dl>`

# 区块标签（万能）

`<div> 盒子 </div>`

`<style> 嵌入式样式 </style>`

## display标签（转变  之间有间隙（标签之间的空格或文字等造成的），一般不用）

block  转变为块级元素

inline  转变为行内元素（无宽高，由内容撑开）

inline-block  既可以转为行内元素，又有宽高

none  隐藏元素

注意：

1，块级元素的宽可以继承父元素的，但是高不会继承

2，在一个盒模型里，浮动的时候都浮动  否则下面没有浮动的元素会占据已浮动元素的位置

3，行内元素无宽高，但是浮动后就有了宽高，类似于一个行内块。所有的标签都可以浮动

4，如果父元素没有设置高，子元素浮动后就不能撑开父元素

5，浮动起来的元素，如果没有给它设宽高，那么它的宽高默认由其里面的内容撑开

## 清除浮动影响

只需在所有要浮动的元下面加一个div  格式如下：

`<div style="clear:left/right/both"></div>`

# css

层叠样式表  cascading style sheet

## div+css布局方式

按区域划分，div承载的是内容，css承载的是样式

## 引入方式

1，行内样式，在开始标签里面利用style属性写样式

2，嵌入样式表，利用`<style></style>`标签对嵌入到页面任意位置，可以嵌入多个，一般嵌入在头部标签里

3，外部样式表，利用link标签引入外部css文件

4，导入样式表，@import

注意：

1，可以用多种方式引入css

2, 同一种引入方式可与利用多次

3，外部样式表不允许再写style标签对

## 引入方式优先级

行内样式优先级最高

嵌入样式表和外部样式表的优先级一样，谁后引入谁就生效

# 选择器

1，标签名{}

2，.类名{}

3，可以多个类名 中间用空格隔开

4，后代选择器  父 子  如：.box .a{}或div .a{}或div p{}

5, 交叉选择器  如：div.a

6，id选择器   id="..."      调用：#...{}    （id名唯一）

7，群组选择器：用逗号隔开所有的选择器（同时选择多个选择器）

8，*  可以作用所有的选择器

9，父>子 子代选择器

10，+  相邻兄弟选择器   例：.E:nth-child(n) +.E>a  表示父元素里面的第n个子元素后面的第一个相邻兄弟元素里面的a元素

11，~  通用兄弟选择器  例：.E:nth-child(n) ~.E>a  表示父元素里面的第n个子元素后面的所有的兄弟元素里面的a元素

9，叠加性  （样式可以通过多个选择器的样式合成）

10，继承性   （子代可以继承父代的样式）

11，选择器优先级：可通过样式进去比较，也可以通过检查网页代码进去比较。

                  important>行内>交叉或后代>id>类名>标签>*>浏览器预定样式>继承

## 伪类选择器  ：

    ：link    超链接初始样式
    :visited  访问过后的样式
    ：hover   鼠标悬停样式
    :active   鼠标按下时的样式
    
    :not()
    :first-child   例：li:first-child 表示父元素里面的第一个li
    :last-child
    :only-child
    :empty
    :checked
    :nth-child()   例：li:nth-child(n) 表示父元素里面的第n个li
                       li:nth-child(3n)  表示父元素里面的3的倍数的li子元素
     

## 盒模型 

padding（不可设置负值）  

margin  (当上下两个边界冲突时，谁大就依谁，并不累加。可设置负值。

  如果没有设置父级元素的内边距或边框那么他的子元素的边界会和其合并。当浮动后，上下左右的边距就会叠加)  

border

## 有默认样式的标签

body  p  h1-h6  ul  ol  li  dl dt dd pre  form  table....

## 文字对齐方式

text-align:水平对齐

line-height:垂直对齐方式

## 调节字体

font-size  文字大小   px、em

font-weight  文字粗细  bold（加粗）normal（正常）100~900（9级加粗）

font-family  文字字体  可写汉字  也可同时写多个字体，从第一个开始选择  sans-serif(取相似字体)

font-style  文字风格  normal（默认值标准样式）italic （斜体）oblique（倾斜）inherit

color  文字颜色  rgb( , , )    rgba( , , , )最后一个数字代表文字透明度

line-height  行高  px  也可直接写数字不加单位，代表多少倍

letter-spacing: 5px;   设置字间距

## 单行文本超出变成省略号

white-space:nowrap  多出的文本不换行

overflow:hidden  多出文本隐藏（图片一样使用）

text-overflow: ellipsis   隐藏文本用省略号显示

## 多行文本超出变成省略号



## 微调方式

1，可以用行内样式微调（记得改对应的像素）

2，可以使用多个类名微调

## 超链接

`<a herf="">  </a>`

地址可写绝对路径和相对路径

target:网站打开的窗口

title:光标滑上去显示注释

下载图片：href里面写要下载图片的地址，download里面写自己要给这个图片命名的名字

可以通过嵌入图片 达到点击图片跳到对应网站的效果

锚链接 href="#..."    name="..."

## 实体符号

## Iframe 标签  将网页分块链接

属性：href  name  width hright scrolling  frameborder 

## 表格

# 放在table属性里
height  width

border:边框

cellspacing:单元格之间的距离

cellpadding:文字距表格边框的距离

align：表格的对齐方式

bgcolor:表格背景颜色

# 放在tr属性里

align：文本水平对齐方式

valign:文本垂直对齐方式

bgcolor:表格背景颜色

height：高

注：width不起作用

## 放在td属性里

width：宽

height：高

bgcolor:表格背景颜色

colspan:合并列  删除此行的相应列

rowspan:合并行  删除下一行的相应列



| 标签  | 属性名               | 属性值            |                        |
| ----- | -------------------- | ----------------- | ---------------------- |
| table | width/height         | 数字              |                        |
| table | border               | 数字              |                        |
| table | align                | center left right |                        |
| table | cellspacing          | 数字              | 设置表格单元格间距     |
| table | cellpadding          | 数字              | 设置文字和表格边框边距 |
| table | bgcolor              |                   | 设置表格背景颜色       |
| tr    | height  bgcolor      |                   |                        |
| tr    | align                |                   | 设置行文本水平对齐方式 |
| tr    | valign               | top middle bottom | 设置行文本垂直对齐方式 |
| td    | width/height         |                   |                        |
| td    | bgcolor/align/valign |                   |                        |
| td    | rowspan              | 数字              | 合并行                 |
| td    | colspan              | 数字              | 合并列                 |



## 实体

|效果|代码|效果|代码|
|-----|-----|-----|-----|
|"|`&quot;`|&|`&amp;`|

## 表单 (存放用户信息)

`<form action="url" method="get/post" name="" > </form>`

name:表单提交时的名称

action:提交到的地址

method:提交方式，默认get

post:提交时看不到地址  一般提交大量数据

get:提交时能看到地址 一般提交少量数据   安全性不好

控件：用户名  密码框  单选框  复选框  上传文件  隐藏区域  普通按钮  提交按钮  重置按钮 图像按钮 下拉列表 多行文本 label标签

注意：

1.所有的控件必须用form表单包起来，否则不能提交

2，控件必须设置的属性有：type（控件类型）  value(收集填写的信息  自定义，可以为汉字)  name（告诉我们提交的信息是什么  自定义，一般为英文）  

3，select控件里option最终提交的值是value的值，文本只是提示
## 元素集(将元素分类)

`<fieldset> <legend> </legend> </fieldset>`  

# css高级效果

## 单行文本超出的隐藏

white-space:nowrap;

overflow:hidden;

text-overflow: ellipsis;

## 多行文本超出的隐藏


display: -webkit-box;

-webkit-box-orient: vertical;
 
overflow: hidden;

text-overflow: ellipsis;

## 阴影

box-shadow:0px 0px 10px 10px #95ff95 inset ;

          x方向 y方向 模糊程度  扩散程度  颜色  内（外不用写）
          
 ：hover（一般和伪类选择器一起用达到想要的效果）
 
过度

transition:all 100ms linear;  （不是写在伪类选择器里  而是在选中
的选择器里）

          属性  时间  变化方式
          
放大（一般和伪类选择器配合使用  达到鼠标一上去就放大的效果）

transform:scale(1,1);   水平和垂直方向同时缩放1倍  也可写一个值 代表水平和垂直一样

## 定位

position :relative(相对)下面的元素不会顶上去  脱离文档流 占据原来的位置   原来的位置

          absolute(绝对)下面的元素会顶上去  脱离文档流  一般用absolute    位于具有定位属性的父辈元素的左上角（父辈一般用relative）
         
left:    top:  （right:  bottom:）

注：

定位之后，margin和padding都不生效了  浮动的时候padding还会生效，但margin不生效

后定位的元素的乘积比之前的高  调节乘积： z-index:数字;   (数字越大乘积越高)

定位后靠左垂直居中：

         
         
        
定位后靠右垂直居中：
     
              right:0;
              top:0;
              bottom:0;
              margin-top:auto;
              margin-bottom:auto;
                 
定位水平垂直居中：

         left:0;
         top;0;
         right:0
         bottom:0
         margin-top:auto;
         margin-bottom:auto;
         margin-left:auto;
         margin-right:auto;
        

# 伪元素（设置宽高 然后定位）

::before

::after

E::first-line   伪元素选择器     选择匹配E元素内的第一行文本

E::first-letter  伪元素选择器     选择匹配E元素内的第一个字符

# css3新增选择器属性

E[attr]  属性选择器   选择匹配E的元素，且该元素定义了attr属性。E选择符可以省略，表示选择定义了attr属性的任意类型的元素。

E[attr="bar"]  属性选择器    选择匹配E的元素，且该元素attr属性值为"bar"

E[attr~="bar"]  属性选择器   选择匹配E的元素，且该元素定义了attr属性，attr属性值是一个以空格符分隔的列表，其中一个列表的值为"bar"，E选择符可以省略。

E[attr!="en"]   属性选择器   选择匹配E的元素，且该元素定义了attr属性，attr属性值是一个用连字符（-）分隔的列表，值以"en"开头。

E[attr^="bar"]  属性选择器   选择匹配E的元素，且该元素定义了attr属性，attr属性值以"bar"开始。E选择符可以省略，表示可匹配任意类型的元素。

E[attr$="bar"]  属性选择器   选择匹配E的元素，且该元素定义了attr属性，attr属性值以"bar"结束。E选择符可以省略，表示可匹配任意类型的元素。

E[attr*="bar"]  属性选择器   选择匹配E的元素，且该元素定义了attr属性，attr属性值包含"bar"。E选择符可以省略，表示可匹配任意类型的元素。

## 伪类选择器

E:root   选择匹配E所在文档的根元素。在（X）HTML文档中，根元素就是html元素，此时该选择器与html类型选择器匹配的内容相同。

E:first-child    选择匹配E的元素，且该元素为父元素的第一个子元素

E:last-child     选择位于其父元素中最后一个位置，且匹配E的子元素。

E:nth-child(n)   选择所有在其父元素中第n个位置的匹配E的子元素。

E:nth-last-child(n)    选择位于其父元素中且匹配E的最后第n子元素。

E:nth-last-of-type(n)  选择父元素中倒数第n个位置，且匹配E的子元素。

E:first-of-type   选择位于其父元素中且匹配E的第一个同类型的子元素。该选择器的功能类似于 E:nth-of-type(1)

E:last-of-type    选择位于其父元素中且匹配E的最后第一个同类型的子元素。该选择器的功能类似于 E:nth-last-of-type(1)

E:only-child      选择其父元素只包含一个子元素，且该子元素匹配E。

E:only-of-type    选择其父元素只包含一个同类型的子元素，且该子元素匹配E。

E:empty         选择匹配E的元素，且该元素不包含子节点。

     注意：
     （1）
     这些选择器选择的都是E元素，后面的伪类只是对他的修饰。
     例如E:first-child选择的是E元素并且E必须是作为第一个子元素出现的，而不是选择E的第一个子元素
     
     （2）
     参数n可以是数字（1、2、3）、关键字（odd、even）、公式（2n、2n+3）参数的索引从1开始。
     tr:nth-child(3)匹配所有表格中第3排的tr；
     tr:nth-child(2n+1)匹配所有表格的奇数行；
     tr:nth-child(2n)匹配所有表格的偶数行；
     tr:nth-child(odd)匹配所有表格的奇数行；
     tr:nth-child(even)匹配所有表格的偶数行；
     E:nth-last-child(n) 选择所有在其父元素中倒数第n个位置的匹配E的子元素
     E:nth-of-type(n) 选择父元素中第n个位置，且匹配E的子元素。
      
      注意，所有匹配E的子元素被分离出来单独排序。非E的子元素不参与排序。参数n可以是数字，关键字、公式。例：p:nth-of-type(1)。

## 选择器优先级

    一个选择器的优先级由四个数字a,b,c,d确定。
    当比较两个选择器时，先比较a，a值大的优先级高，如果a相等则比较b，b值大的优先级高，以此类推。
    因此，无论b的值多大，也不会对a值的比较造成影响。
    a由style确定，如果一个属性由元素上的style属性定义则a为1，否则a为0; 
    b是id的数量 
    c是class和伪类以及属性选择器的数量，后代选择器 
    d是标签选择器以及伪元素的数量 
    e是通用选择器 伪元素： 对于div内部的元素，比如这个first-line first-letter before after 伪类：选择原宿本身，比如hover visited link active first-child focus

    示例
     *             {}  /* a=0 b=0 c=0 d=0 -> specificity = 0,0,0,0 */
     li            {}  /* a=0 b=0 c=0 d=1 -> specificity = 0,0,0,1 */
     li:first-line {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
     ul li         {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
     ul ol+li      {}  /* a=0 b=0 c=0 d=3 -> specificity = 0,0,0,3 */
     h1 + *[rel=up]{}  /* a=0 b=0 c=1 d=1 -> specificity = 0,0,1,1 */
     ul ol li.red  {}  /* a=0 b=0 c=1 d=3 -> specificity = 0,0,1,3 */
     li.red.level  {}  /* a=0 b=0 c=2 d=1 -> specificity = 0,0,2,1 */
     #x34y         {}  /* a=0 b=1 c=0 d=0 -> specificity = 0,1,0,0 */
     style=""          /* a=1 b=0 c=0 d=0 -> specificity = 1,0,0,0 */

# github

1.github新建仓库
2.本地新建文件
  1.git init
  2.添加readme.md
  3.git add *
  4.git commit -m "说明"
  5.git remote add origin https://github.com/yang1633/YY.git
  6.git push -u origin master
  
第二次

1. git add*
2.git commit -m "说明"
3. git push  





















