**CSS样式规则**

格式：选择器{ 属性：属性值；属性：属性值；}

规则：

1. 选择器用于指定CSS样式作用的html对象，花括号内是具体的样式
2. 属性和属性值以“键対值”的形式出现 
3. 属性是对指定的对象设置的样式属性，例如字体大小，文本颜色等
4. 属性和属性值之间用英文”:”链接 不是等号
5. 多个键值对之间用英文”;”区分

**字体设置**

CSS Unicode字体

微软雅黑 \5FAE\8F6F\96C5\9ED1

宋体 \5B8B\4F53

尽量只写unicode字体 写宋体和微软雅黑

CSS中注释方式：/*xxxxx*/ 

**设置字体样式：font-family:****”****xxx****”**

**设置字体字号：font-size:****”****xxpx****”**

**字体字号常用技巧：**

**网页中正文普遍使用****14px**

**若有设置多个字体，则字体之间应用****英文逗号隔开**

**中文字体需要加英文双引号****，英文字体不需要，且****英文字体应在中文字体之前**

**若字体中包****含空格、π、$等符号****，无论是英文还是中文字体都****必须加引号**

**尽量使用系统默认字体**

**设置字体粗细**

**Font-weight:**

**可用属性值包括normal（即400）、bold（即700）、bolder、lighter、100-900之间100的整倍数**

**设置字体风格**

**Font-style:**

**可用属性值包括normal,italic(斜体)**

**字体综合设置**

**选择器{font：font-style font-weight font-size/line-height font-family；}**

**注意：**

**不能更换顺序，以空格隔开**

**不需要设置的属性可以忽略**

**选择器**

**标签选择器** 

格式：

标签名{属性1：属性值1；属性2：属性值2；属性3：属性值3；}

**类选择器**

格式

.类名{属性1：属性值1；属性2：属性值2；属性3：属性值3；}

标签调用时用class=“类名”即可

命名规范：

1. 长名称或词组可以使用中横线来为选择器命名
2. 不建议使用“_”下划线命名css选择器
3. 不要纯数字、中文等命名，尽量使用英文字母

**多类名选择器**

即一个标签带多个类名，从而实现灵活自由搭配

例：<div class="font20 blue">傻逼</div>

	<div class="font14 blue">憨憨</div>

	<div class="font20 orange">傻逼</div>

	<div class="font14 orange">傻逼</div>

1.样式显示效果跟html中的类名先后顺序无关

2.各个类名中间用空格隔开

**交集选择器**

<style>

标签名.类名{}

</style>

**并集选择器**

<style>

标签名,

标签名,

标签名,

标签名{}      一般上下写

</style>

**Id选择器**

语法格式：

\#id名{}

<xx id=””></xx>

**Id与类选择器区别：一个id只能用于一个标签，类可以用于多个标签。**

**链接伪类选择器**

语法格式

**：link{}  设置未点击链接时链接的样式**

**：visited{} 设置点击链接后链接的样式**

**：hover{}  设置鼠标移动到链接时的样式**

**：active{}  设置鼠标点击链接且不松开时的样式**

注意：必须按照以上**lvha**的顺序

一般工作不需要用到active和visited，所以有以下便捷写法*/

​		a{color:gray;}a:hover{color:red;}

**结构伪类选择器(原理:先找到XX元素的父元素，再找这个父元素的第指定个元素，如果不与xx元素相同则无视。即是相对于父元素的结构伪类）**

**n是从0到指定的元素个数**

xx:first-child{}     选择xx元素中的第一个子元素

Xx:last-child{}     选择xx元素中的最后一个子元素

Xx：nth-child（y）{}  选择xx元素中的第y个子元素

Xx：nth-child（n）{}  选择所有子元素

Xx：nth-child（even）{} 选择所有第偶数个子元素

Xx：nth-child（odd）{} 选择所有第奇数个子元素

Xx：nth-child（2n）{} 选择所有第偶数个子元素

Xx：nth-child（2n+1）{}   选择所有第奇数个子元素

Xx：nth-last-child（）{} 与上面相同，但是是倒数

xx：nth-child（-n+y）{} 选择前y个

xx:nth-of-type(n){}  只认定xx元素同级元素中所有xx元素。即所有xx元素中的第n个

xx:nth-last-of-type （）{} 倒数

**兄弟伪类选择器**

**xx + yy {}  选择在xx后面的yy元素**

**xx ~ yy{} 选择xx之前的yy元素**

**伪元素选择器**

X：：first-letter{}  选中x标签中文档的第一个字

X：：first-line{} 选中x标签中文档的第一行

X：：selection{} 使选中的文字发生实时变化（只能改变显示样式不能改变内容大小）

X：：before{content：”xx”;}在x文档的开头添加文字xx

X：：after{content:”xx”；}在x文档的结尾添加文字XX

**伪元素的本质**

**伪元素本质为行内元素，改为块级元素(或者浮动、定位）后可以设置宽高，伪元素不占位置。设置：before和：after时必须设置content属性，否则伪元素不起作用**

**后代选择器**

父标签 子孙标签{}

**可以选择父标签内的所有对应子标签、孙标签、重孙标签。。。**

**子元素选择器**

父标签>字标签{}

**只能选择父标签的亲生儿子标签。**

**属性选择器**

**状态选择器**

| [:empty](https://www.w3school.com.cn/cssref/selector_empty.asp) | p:empty        | 选择没有子元素的每个 <p> 元素（包括文本节点）。 | 3    |
| ------------------------------------------------------------ | -------------- | ----------------------------------------------- | ---- |
| [:target](https://www.w3school.com.cn/cssref/selector_target.asp) | #news:target   | 选择当前活动的 #news 元素。                     | 3    |
| [:enabled](https://www.w3school.com.cn/cssref/selector_enabled.asp) | input:enabled  | 选择每个启用的 <input> 元素。                   | 3    |
| [:disabled](https://www.w3school.com.cn/cssref/selector_disabled.asp) | input:disabled | 选择每个禁用的 <input> 元素                     | 3    |
| [:checked](https://www.w3school.com.cn/cssref/selector_checked.asp) | input:checked  | 选择每个被选中的 <input> 元素。                 | 3    |
| [:not(*selector*)](https://www.w3school.com.cn/cssref/selector_not.asp) | :not(p)        | 选择非 <p> 元素的每个元素。                     | 3    |

not（）括号里可以是类名id名属性等等

target样式：可以为锚点目标元素添加样式，当目标元素被触发为当前锚点链接的目标时，调用此样式

语法 目标链接：target {样式;}

**颜色**

**CSS颜色三种表达方式**

**1.直接用名字表示 color：red**

**2.用16进制代码表示  color：#ffb100**

**3.用rgb代码表示 rgb（192，255，252） 分别代表红绿蓝，16进制数**

**4.rgba（x，x，x，x）最后一个数值可以设置半透明度**

**5.hsl（颜色，饱和度，亮度）；  颜色0~360  饱和度、亮度0%~100%**

**行高对齐和首行缩进**

行间距：line-height：xx px;

首行缩进  text-indent：xx em；

字间距:letter-spacing

**文字阴影**

Text-shadow:水平位置(px) 垂直位置(px) 模糊距离(px) 阴影颜色(rgba);

**CSS书写规范**

**1.选择器与花括号之间必有空格**

**2.属性名与冒号之间不允许有空格，冒号后必须有空格**

**3.属性值后必须加分号**

**4.当选择器有多个并行标签时，应上下逗号分开**

**5.选择器的嵌套尽量不超三层** 

**6.不同属性应另起一行**

**CSS样式表**

**内部样式表**

<head>

<style type=’’text/CSS’’>

选择器 {属性1：属性值1；属性2：属性值2；属性3：属性值3；}

</style>

</head>

**行内样式表**

<标签名 style=’’属性1：属性值1；属性2：属性值2；属性3：属性值3；”>

**外部样式表**

<head>

<link href=’’css的路径’’ type=’’text/css’’ rel=’’stylesheet’’ />   是个单标签

</head>

总结：推荐使用外部样式表

**标签显示类型**

**块级标签**

如<h1> <p> <div> <ul> <ol> <li>等

块级元素特点：

1. 总是从新行开始
2. 高度、行高、外边距以及内边距都可以控制
3. 宽度默认是容器的100%
4. 可以容纳内联元素和其他块元素

**行内元素**

如<a> <strong><b><em><i><del><s><ins><u><span>等

特点：

1. 和相邻行内元素在一行上
2. 高宽无效，但水平方向的padding和maigin可以设置，垂直方向的无效
3. 默认宽度是它本身内容的宽度
4. 行内元素只能容纳文本或其他行内元素

注意：文字标签里不能放块级元素。链接里不能再放链接

**行内块元素**

如<img/><input/><td>等

特点：

1. 和相邻行内元素在一行上，但是之间会有空白缝隙
2. 默认宽度就是它本身内容的宽度
3. 高度，行高，外边距以及内边距都可以控制

**背景图设置**

Background-img:url（）；背景图地址

Background-color:；设置背景颜色

Background-repeat:；设置平铺方式  有no-repeat、repeat-x、repeat-y、space、round选项，分别对应全平铺，x轴方向平铺，y轴方向平铺,图片不缩放并增加空隙后平铺，图片缩放后使其紧贴平铺 

**设置背景图位置**

Background-position：x轴方向像素 y轴方向像素；

Background-posiiton：方位词 方位词；（无先后顺序之分）top bottom left right center

Background-position：方位词+y像素（x像素+方位词）；

**背景图平铺开始位置**

background-origin:border-box,padding-box,content-box(即从border、padding、content开始平铺）

bcakground-clip:border-box,padding-box,content-box(即分别只显示border及以内、padding及以内、content的内容）

**背景附着**

Background-attachment：scroll（fixed） 前者为默认随对象内容滚动，后者为背景图像固定 local

背景简写：background：color  url 平铺方式 滚动方式 位置;（尽量采用此顺序）

背景半透明：在颜色设置中采用rgba（x，x，x，0.x）最后为透明度数值

**背景缩放：**

Background-size：xx px xx px；   

Background-size：xx% xx%；

Background-size：contain；    自动调整缩放比例保证图片完整显示

Background-size：cover；    自动调整缩放比例保证图片填充满背景区域

**多背景图片**

Background-image：url（），url（）；

Background：url（xxxx）……，url（xxx） ……；   不同图片以逗号隔开

**凹陷文字效果**

突出效果：

div:first-child{

​				text-shadow: 2px 2px 2px #000,

​							 -1px -1px 1px #fff;

​		}

凹陷效果：

​		div:last-child{

​				text-shadow: 1px 1px 1px #fff,

​							 -2px -2px 2px #000;

​		}

小技巧 将行距设置为盒子高度即可使文本垂直居中

Text-decoration：none 不设置下划线

Text-decoration：underline 设置下划线

Text-decoration：overline 设置上划线

Text-decoration：line-through 设置穿过文本的一条线

**CSS三大特性:层叠性、继承性、优先级**

**层叠性**

当同个标签设置样式属性不同值出现冲突时，则依照就近原则以最后的样式属性为准。

**继承性**

子元素能继承父元素的样式

**优先级**

**CSS Speciality 权重值：**

**继承或\*的贡献值   0,0,0,0**

**每个元素标签的贡献值 0,0,0,1**

**类、伪类、元素选择器的贡献值 0,0,1,0**

**Id选择器的贡献值 0,1,0,0**

**行内样式贡献值 1,0,0,0**

**！Important的贡献值 ∞无穷大**

**注意：**

**权重可以叠加 如：div ul li 的贡献值为0,0,0,3**

**数位之间没有进制**

**继承的权重为0**

**盒子边框**

Border-color：  设置边框颜色

Border-width： 设置边框厚度

Border-style： 设置边框类型

Style属性值有： 

1. 实线solid
2. 虚线dashed
3. 点线dotted
4. 双实现double

**不同方向边框的写法**

border-top（left、right、bottom）-width（color、style）

**边框综合写法**

Border：width style color

**合并细线表格**

Border-collapse：collapse

**圆角矩形**

Border-radius:xxpx(xx%)     设置四个角

Border-radius:xx xx     设置左上右下  左下右上

Border-radius：XX XX XX 设置左上 左下右上 右下

Border-radius：xx xx xx xx   左上 右上 右下 左下

border-radius:xx/xx     设置每个角的水平/垂直方向

border-方位词-方位词-radius：xxpx； 如broder-top-right-radius

border-radius：x1 x3 x5 x7/x2 x4 x6 x8;    x1x2为左上 x3x4右上 以此类推    

**边框图片**

border-image-source：url（）；

border-image-slice：xx fill； 图片切片，不需加单位,即将图片四个边xx像素的宽度作为边框 fill则是将整个图片填充 

border-image-width:xxpx 设置边框背景图宽度 但是不影响内容放置

border-image-outset:0  边框扩展，一般为0

border-image-repeat:repeat/round (前者直接平铺 后者缩放后平铺）

简写 border-image:source slice /width/outset repeat;

**盒子内边距**

Padding：xx     设置四个边距

Padding：xx xx    设置上下 左右边距

Padding：xx xx xx   设置 上 左右 下边距

Padding：xx xx xx xx   设置上 右 下 左 边距

**Firework工具 滴管查颜色 切片查距离**

**清除内外边距**

\* {padding：0；margin：0}

**行内元素只有左右内外边距没有上下内外边距，尽量不要给行内元素指定上下内外边距**

**外边距合并的问题**

垂直相邻的块元素，若上面的元素有margin-bottom，下面额块元素有margin-top，则他们之间的外边距之和不是两者相加而是两者较大者。这种现象被称为相邻块元素垂直外边距的合并

解决方法：只设置一个盒子的外边距即可

**嵌套块元素的合并**

对于两个嵌套关系的块元素，如果父元素没有上内边距及边框，则父元素的上外边距会子元素的上外边距合并，合并结果为两者中较大者。

**解决方法：1.为父元素定义1像素的边距或内边距2.可以为父元素添加overflow：hidden**

**盒子尺寸计算**

外盒尺寸=width（height）+padding+border+margin

内盒尺寸=width(height)+padding+border

注意：

1. width和height对行内元素无效
2. 要考虑上下两个盒子的外边距合并
3. 若盒子没有指定高度或宽度（或继承了父元素的高度或宽度），则padding不会影响整体高度或宽度

**盒子模型布局稳定性**

**使用优先级：width>padding>margin**

原因：

1.margin会有外边距合并，还有ie6下面margin加倍的bug

2.padding会影响盒子大小，需要进行加减计算

3.Width没有问题，常用宽度剩余法 高度剩余法来做

**CSS3盒模型**

**1.box-sizing：content-box**   

盒子大小为width+padding+border 为默认值

**2.box-sizing：border-box**  

盒子大小为width 即padding和border包含到了width里面 如果为这个值，则设置padding时不用重新计算

**盒子阴影**

**box-shadow: 0px 10px 10px 10px rgba(0 ,0 ,0 , .3)  inset    分别设置 水平距离 垂直距离 模糊距离 阴影大小 颜色 内阴影/外阴影**

**文档流**

**类型**

**1.普通流：网页内标签正常地从上到下从左到右的排序，如块级元素独占一行，行内元素会依照顺序依次前后排列**

**2.浮动**

**3.定位**

**浮动：指设置了浮动属性的元素会脱离标准普通流的控制，移动到其父元素中指定位置的过程。**

语法：选择器{float：属性值；}

属性值：left、right、none

使用浮动首先要添加标准流父盒，从而防止布局失真

浮动特性

1. 父盒内的盒子设置浮动后会就近对齐父盒子，但不会遮盖padding和margin
2. 兄弟盒子中第一个盒子如果浮动，第二个盒子设置浮动后会与其顶部对齐。若第一个盒子不浮动，第二个盒子设置浮动后顶部会与其底部对齐

元素（包括块级和行内）添加浮动后，都会具有行内块元素的特性

总结：float==>浮漏特

浮：加了浮动的元素盒子是浮起来的，漂浮在其他的标准流盒子上面

漏：加了浮动的盒子，不占位置的，他浮起来了，他原来的位置漏给了标准流的盒子

特：特别注意要和标准流父级搭配使用。

**清除浮动**

**在一般情况下，考虑到子盒子的内容变化，父盒子都不方便设置高度。子盒子没有浮动时会自动撑开父盒子。如果子盒子浮动，则父盒子高度会变为0，导致其他盒子占据位置。**

**清除浮动就是解决没有设置高度的父盒子在子盒子浮动后高度变为0的现象**

**解决方法**

**1.在父盒子中添加overflow除了visible以外的属性值**

也相当于堵上一堵墙

优点：简单

缺点：溢出隐藏

**2.额外标签法：父盒子内最后一个浮动盒子的后面添加空标签，且将该标签的clear属性值设置为both**

**.clear {**

​			**clear: both;****}**  **清除浮动的影响**

相当于设置一堵墙，防止浮动盒子影响外部

优点：通俗易懂，书写方便

缺点：添加了无意义的标签

**3.用after伪元素清除浮动（推荐）**

**父盒子类名添加 clearfix**

**.clearfix:after {**

​			**content: '.';**

​			**display: block;**

​			**height: 0;**

​			**visibility:hidden;**

​			**clear: both;** 

​		**}**

**.clearfix {\*zoom:1;} //兼容ie老版本**

优点：结构语义化正确

缺点：ie6-7不支持：after兼容性问题

**4.用before和after双伪元素清除浮动（推荐）**

**父盒子类名添加clearfix**

**.clearfix:before,.clearfix:after {display:table;content:****’** **‘****;}**

**.clearfix:after {clear:both;}**

**.clearfix {\*zoom:1;}**

优点：结构语义化正确

缺点：ie6-7不支持：after兼容性问题

**定位（包括定位模式和边偏移）**

**边偏移**

Top bottom left right

**定位模式**

**语法：**

**Position：{属性值；}**

**属性值：**

1. **静态定位static：**
2. **相对定位relative：**
3. **绝对定位absolute**
4. **固定定位fixed**

**Static定位：**

默认，该定位下无法使用边偏移属性

**Relative定位：**

定位后可通过边偏移改变位置，是以自身左上角为基准。不脱标，依旧是标准流，原先位置保留

**Absolute定位：**

可通过边偏移改变位置，完全脱标不占位置。

子盒子设置为absolute后，父盒子必须定位为任何定位类型，子盒子才能以父盒子为基准设置边偏移改变位置，否则会乱跑

**子绝父相：一般子盒子设置为绝对定位后，父盒子要设置为相对定位较好**

**水平/垂直居中：盒子设置绝对定位后，margin中的auto无效（具体数值有效）**

要居中一般是以：1首先left50%2.然后走外边距负的一半值即可

如：left：50%；margin-left：-xxpx；

Top：50%；margin-top：-xxpx；

或者 left：父盒子宽度一半减去子盒子宽度一半；top：父盒子高度一半减去子盒子高度一半

**Fixed定位**

1. 固定定位的元素跟父亲没有任何关系，只认浏览器
2. 完全脱标,不占位置,不随着滚动条移动

**叠加次序**

1. index:正整数、负整数、0

注意

1.index默认属性值为0，取值越大，定位元素在层叠元素中越居上

2.如果取值相同，则按顺序后来居上

3.后面数字不能家单位

**4.****只有相对定位绝对定位固定定位有这个属性。**

**定位总结** 

![img](D:\typora\images\image4.jpeg)

**固定绝对定位模式转换**

跟浮动一样,元素添加了绝对定位和固定定位之后,元素都会变成行内块模式

也就是；如果行内元素添加了绝对定位和固定定位后,可以不用转换模式,直接添加高度宽度。

**Display和visibility的使用**

Display设置或检索对象是否及如何显示

Display：none 隐藏对象

Display：block除了转换为块级元素之外还有显示元素的意思

特点：隐藏之后，不再保留位置

Visibility

设置或检索是否显示对象

Visible：对象可视

Hidden：对象隐藏

特点:隐藏之后,继续保留原有位置

**Overflow溢出**

属性值

Visible:不剪切内容也不添加滚动条 （默认）

Auto：超出自动显示滚动条,不超出不显示滚动条

Hidden：不显示超出对象内容的尺寸,超出的部分隐藏掉

Scroll：不管超出内容否,总是显示滚动条

**CSS高级技巧**

**鼠标样式**

cursor: default;    小白（默认） 

cursor: pointer;    小手

cursor: text;     文本	

cursor: move;    移动

**取消轮廓线**

语法：

Outline : width style color;

一般为none

**防止拖拽文本**

textarea {resize: none;} 

**行内块和文字对齐（一些低版本浏览器中盒子内的图片可能底部出现缝隙）**

Vertical-align:实现行内元素和行内块元素的对齐，对于块级元素无效

属性值包括 top、middle、bottom、baseline（默认）

一般选用middle 

**去除图片底侧缝隙**

1. 将图片转为块级元素 display：block
2. 将图片顶部对齐或者中线对齐  vertical-align：top（middle）  

**Word-break用法**

Word-break：normal     默认方式

Word-break：break-all  允许单词中换行

Word-break：keep-all 只能在半角空格或连字符处换行

**White-space用法**

White-space：normal  默认处理方式	

White-space：nowrap 强制在同一行显示所有文本，直到1文本结束或遭遇br才换行

**Text-overflow使用**

Text-overflow:clip   不显示省略标记,而是简单的裁切

Text-overflow:ellipsis 当对象文本溢出时显示省略标记

**注意：****必须先使用white-space：nowrap和overflow：hidden两个属性后才能使用这个**

**精灵技术**

即将所有背景图通过一张图来显示

先设置对应元素的宽高，再设置background-position,注意此处应为负值

**字体图标**

网站：icomoon.io

**将下载后的icomoon文件夹中的font文件夹放到与html文件同个文件夹中，然后声明，声明后打开icomoon文件夹中的html文件复制小空格到目标元素中，再设置font-family。**

追加字体文件要利用icomoon文件夹中的selection文件

**滑动门技术**

固定语法

a里面包含span

不能设置宽度

A负责左边框，span负责右边框且背景图位置应设置为right

记得转换为块元素或行内块元素

**2D效果**

**过渡效果**

Transition：变化的属性 过渡时间 时间曲线 开始时间

变化的属性：所有属性过渡效果一样时可以用all代表，不相同则需逗号隔开重写

过渡时间：s为单位，必须写，包括0

时间曲线：linear匀速 ease变慢 ease-in 加速  ease-out减速 ease-in-out先加速后减速

开始时间：s为单位，必写

Transition要写在变化的元素内而不是元素的hover内

**移动**

Transform:translate（xxpx xxpx）； 第一个为x轴方向移动距离,第2个为y轴方向移动距离

盒子居中新方法：left、top（浏览器一般长度） 然后 transform：translate（-盒子一半宽度 -盒子一半长度）

translate如果用百分比则是以元素本身长宽为基准

translateX：沿x轴移动

translateY：沿y轴移动

translateZ：沿Z轴移动

**缩放**

Transform:scale（任何正整数） 0-0.99是缩小 大于1是放大

**旋转**

Transform：rotate（xxdeg）； deg是度数单位 

改变旋转中心

Transform-origin：xxpx xxpx（方位词 方位词）；（写在变化元素标签内，而不是动作内）

Transform-style  指定嵌套元素如何在3d空间中呈现

属性值 flat（默认值）：所有子元素在2D平面呈现

Preserve-3d：表示所有子元素在3D空间中呈现

translate3d(x方向的偏移，y方向的偏移，z方向的偏移）

scale3d（x方向的缩放，y方向的缩放，z方向的缩放）

rotate3d（x方向向量，y方向向量，z方向向量，旋转角度） 

**倾斜**

Transform：skew（xxdeg xxdeg）； 第一个为x轴方向倾斜,正值向右负值向左

第二个为y轴倾斜方向,正值向上负值向下

**Web坐标轴**

左右是x轴负、正方向

上下是y轴负、正方向

朝外朝内是z轴正负方向

rotateX：绕x轴旋转

rotateY：绕y轴旋转

rotateZ：绕z轴旋转

**透视属性**

Perspective：xx px;

Persperctive 代表着观察者眼睛到屏幕的距离,赋予3d效果

数值越小透视效果越好 数值越大透视效果越差

perspective-origin:xxpx  xxpx；设置观察的角度

**动画**

**引用动画**

**Animation:动画名称 持续时间 时间曲线 启动时间 播放次数 是否反方向**

animation-fill-mode设置动画结时的状态

属性值：forward 动画结束时保持状态 backward 动画结束时不保持状态，在设置了动画延时的前提下，如果动画有初始状态，那么会立刻进行到初始状态  both：会保留动画结束的初始状态,在设置了动画延时的前提下，如果动画有初始状态，那么会立刻进行到初始状态 

animation-play-state:running(paused)设置动画播放状态

**动画持续时间还有个属性值为steps（n）  就是将动画分为n步执行**

**定义动画**

@keyframes 动画名称 {from{}   to{}       }或者 {百分数{} 百分数{} 百分数{}}

时间曲线同transition

播放次数 infinite无限次播放

方向：

1. normal 正常方向
2. Reverse 反方向
3. Alternate 先正常后反方向，不断交替
4. Alternate-reverse： 先反方向再正常，不断交替

**多列布局**

column-count:设置分成的列数

column-rule：宽度 线条样式 颜色；     设置列之间的样式

coulumn-gap：xxpx；    设置列之间的距离

column-width：设置每一列的宽度  如果设置宽度比当前列数所默认的宽度小，则不改变，如果比较大，则取其值并铺满整个浏览器；

column-span：设置某个元素跨越的列数，只有1和all两个选项；

**BFC（块级格式化上下文）：是一个独立的渲染区域,只有Block-level box参与,它规定了内部的Block-Level Box如何布局，并且与这个区域外部毫不相干**

**具有BFC条件的元素模式：block、list-item、table**

触发BFC的属性：

1. float属性不为none
2. Position为absolute或fixed
3. Display为inline-block、table-cell、table-caption、flex、inline-flex
4. Overflow不为visible

**BFC特性**

1. BFC中，盒子从顶端垂直的一个接一个排列
2. 属于同一个BFC的两个相邻盒子的margin会发生重叠   
3. BFC中，每一个盒子的左外边缘会触碰到容器的左边缘
4. BFC的区域不会与浮动盒子产生交集，而是紧贴浮动边缘   （用于产生浮动盒子旁边的自适应盒子）
5. 计算BFC的高度时，自然也会检测浮动的盒子高度  （用于清除浮动）

**作用**

1. 清除浮动

给父盒子激活BFC就可以

1. 解决外边距合并

用另一个BFC盒子将两个盒子中的一个包起来，即可解决

1. 产生浮动盒子旁的自适应盒子

将新盒子激活BFC，就不会跑到浮动盒子下面，而是与其紧贴

**渐进增强：构建网站时先满足低版本再考虑高版本**

**优雅降级：与上者相反**

**浏览器前缀**

-webkit-：chrome ，safari，android，browser

-moz-：firefox

-o-：opera

-ms-：ie，edge

-khtml-：konqueror

**背景颜色渐变（因为兼容性问题严重，所以需要加浏览器前缀）**

线性渐变：

background:-浏览器前缀- linear-gradient(渐变起始位置， 起始颜色， 结束颜色)；

background:-浏览器前缀- linear-gradient(渐变起始位置， 起始颜色 百分比， 结束颜色 百分比)；用渐变起始位置就需要加浏览器前缀

background:linear-gradient（point/angle,颜色 位置，颜色 位置 颜色 位置....）

point：to left(从右到左）,to right,to top,to bottom（默认值）

angle：对应上面为270deg，90deg，0deg，180deg

用point/angle就不用加浏览器前缀

径向渐变

background:radial-gradient(形状 大小 发散位置，颜色 位置，颜色 位置，颜色 位置，。。。）；

形状：默认为ellipse（即自动适配当前形状），circle（圆形）

大小：closest-corner、closest-side、farthest-corner、farthese-side

发散位置：at xxpx xxpx或at 方位词 方位词（默认在正中心）

重复渐变

repeating-radial(linear)-gradient:属性值同上

**三大标签优化**

**Title** 

<title>标题</title>

长度：google（35中文） baidu（28个中文）

最先出现的词语的权重越高

建议：首页标题：网站名（产品名）-网站的介绍

**Description**

<Meta name=“description” content=“内容” />

搜索结构的部分摘要，即简要说明我们的网站是做什么的

注意：不要超过120个汉字，用英文逗号

**Keyword**

<Meta name=“keyword” content=“内容” />

页面关键词，搜索引擎关注点之一，限制在6-8个关键词左右

布局时为了防止浏览器缩小时两个元素重叠，可以将两个元素先定位到相反的位置，然后再用translate移动到目的位置

实现打字动画效果，可以先将完整文字图片的宽度改为0，再利用trasnform将宽度改回来，并用steps分步执行