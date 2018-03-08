# 前端基础 - css #
CSS(Cascading Style Sheets)，以html为基础的层叠样式表，用于网页布局。

- 主要内容包含:

	- 选择器
	- 浮动
	- 盒模型
	- 定位
	<br>
- 书写位置包含:
	- 内嵌式
	
		```
		<head>
			<style type="text/css">
			
			</style>
			...
		</head>
		```
	- 行内式
	
		```
		<div style="color: red; font-size: 20px; width: 100%; height: 100%;">什么鬼5</div>
		```
	
	- 外联式
	
		```
		<head>
			<link  rel="stylesheet"  href="1/2/type3.css">
			...
		</head>
		
		```

- **CSS特性**包括:
	- 层叠性: 不同选择器定义相同的样式内容，<font color=red>**覆盖情况与选择器定义顺序有关**</font>。
	
	- 嵌套继承性: 内层标签可继承外部标签的样式有: `color、font-size、font-family、font-weight、font、line-height`，** 而`<a href="#"></a>、<h1></h1>、....`不能继承。**
	
	- 优先级 优先级可叠加

		```
			/* 优先级 = 2 */
			.two{
				color: green;
			}
			
			/*优先级 = 1 + 2 + 1 = 4 */
			div.one p{
				color: pink;
			}
		 	
			/*优先级 = 1 + 2 = 3 */
			p.two{
				color: yellow;
			}
		         
			/*优先级 = 1 */
			p{
				color: red;
			}
			........................................................................................................................................
			<!-- 使用 -->
			<div class="one">
				<p class="two">文字</p>
			</div>
			
			p标签内的文字颜色为 pink
		```
		优先级以下:
		
|样式与选择器|优先级(类比值)|
|-				|:-:|
|!important		|5|
|行内样式		|4|
|id选择器 		|3|
|class选择器		|2|
|标签选择器		|1|
|默认样式/嵌套继承性|0|

	当样式冲突时,
		- 先判断是否样式指向同一个标签 , 
			- 当指向相同标签时 , 
				- 先通过----与选择器定义顺序有关----进行判断;
				- 再通过----优先级叠加----进行判断 , 使用优先级高的样式;
	
---
### 语法结构 ###
```
	选择器{
		属性1:值1;
		属性2:值2;
		...
	}

```
---
### 选择器 ###
选择谁的过程。

属性|赋值|释义
-|-|-
`color`|`color: rgb(0, 0, 0);` |颜色
`background-color`|`color: rgb(0, 0, 0);`|背景色
`width/height`|`30px`|宽高
`font-size`|`20px`|字体大小
`font-family`|`font-family: "微软雅黑";`|文字(多个)字体
`font-weight`|`100~900`,`normal`,`bold(700~900)`|文字权重
`font-style`| `italic`	文字斜体显示<br> `normal`	文字正常显示|设置文字样式
**`font`**|**`font:  italic 20px "微软雅黑" bold;`**|**属性连写**
`line-height`|`line-height: inherit;`|行高

<font color=red>**font 属性连写必须有 `font-size`与 `font-family`，并且顺序不可换;**</font>

字体名称|英文名称|Unicode 编码
-|-|-
宋体|SimSun|\5B8B\4F53
新宋体|NSimSun|\65B0\5B8B\4F53
黑体|SimHei|\9ED1\4F53
微软雅黑|microsoft yahei|\5FAE\8F6F\96C5\9ED1	
楷体_GB2312|KaiTi_GB2312|\6977\4F53_GB2312
隶书|LiSu|\96B6\4E66
幼园|YouYuan|\5E7C\5706
华文细黑|STXihei|\534E\6587\7EC6\9ED1
细明体|MingLiU|\7EC6\660E\4F53
新细明体|PMingLiU|\65B0\7EC6\660E\4F53


#### 1. 基础选择器 ####
##### I. 标签选择器

```
	html的标签名{ 属性:值; 属性:值; ...}
	
	例如:
		h3 {
			width: 100%;
			height: 100%;
			color: rgb(0,0,0);
			background-color: #FFFFFF;
			font-size: 30px;
		}
```

##### II. ❤ 类选择器❤ 与 ❤伪类选择器 ❤
- 类选择器
	**一个标签可以调用多个类样式，之间用空格隔开。**
	```
		.自定义类名{属性:值; 属性:值; ...}
		
		例如:
			<!--定义-->
			<style type="text/css">
				.clzssZ {
					width: 100%;
					height: 100%;
				}
				
				.clzssY {
					color: rgb(0, 0, 0);
					background-color: #FFFFFF;
					font-size: 30px;
				}
			</style>
			
			<!--使用-->
			<p class="clzssZ clzssY">什么鬼0</p>
	
	```
	类的命名规范如下:
	![类的命名规范](https://i.imgur.com/5Enh9M6.jpg)
	
	- 类名的定义**不能以数字/特殊符号（“_”除外）开头**；
	- 类名不能包含汉字；
	- 类名不建议使用标签名或属性名；

- 伪类选择器
	**伪类选择器用于有超链接的标签**。
	```
	/*默认样式*/
	a{
		text-decoration: none; 不显示线
		text-decoration: underline; 下划线
		text-decoration: overline; 上划线
		text-decoration: line-through; 贯穿线
	}
	/*默认样式*/
	a:link{}
	
	/*鼠标放到超链接上的样式*/		
	a:hover{}
	
	/*激活(点击未松开鼠标)状态下的样式*/		
	a:active{}
	
	/*访问过后的样式,缓存可能造成影响*/
	a:visited{}
	
	/*(不重要) 获取焦点（光标）的时候的样式*/	
	a:focus{}
	```

##### III. id选择器
根据控件/标签的id设置样式。
```
	#定义的id名称{属性:值; 属性:值; ...}
	
	例如: 
			#username {
				color: rgb(0, 0, 0);
				background-color: #FFFFFF;
				font-size: 30px;
			}

			<input type="text" name="userName1" id="username" value="TextForInput" maxlength="10" readonly="readonly" disabled="disabled" />
```
- 一个id只能调用一个id样式；
- 不建议多个标签使用同一个id；

##### IV. 通配符选择器 
当前页面**所有标签公共样式**，也就是**全局属性**。

```
	*{属性:值; 属性:值;...}
	
	例如:
		* {
			background-color: darkgoldenrod;
		}

```
---
#### 2. 复合选择器 ####
##### I. ❤ 标签指定式选择器 ❤
```
			h3#username {
				...
			}
			
			<table >
				<caption>
					<h3 id="username">这是一个表格标题</h3>
				</caption>
				...
			</table>
			
			
			p.classA{
				...
			}

			<p class="classA">什么鬼1</p>
```
组合方式有:
- **标签名 + " . " + 类名**
- **标签名 + " # " + id名**

---
##### II. ❤ 后代选择器 ❤
**标签包含的关系。**

组合方式有:

- **标签名 + " "(空格) + 标签名**

	```
		div div{
				color: #B8860B;
			}
	
		<div>
			<!--变色-->
			<div>什么鬼2</div>
		</div>
		<!--不变色-->
		<div>什么鬼3</div>
	```
	
- **选择器名 + " "(空格) + 选择器名**

	```
		div.classC div#di1{
				background-color: chocolate;
		}
	
		<div class="classC">
			<!--变色-->
			<div id="di1">什么鬼4</div>
		</div>
		<!--不变色-->
		<div>什么鬼5</div>
	
	```
- **标签名 + " "(空格) + 选择器名**(将不做演示)
- **选择器名 + " "(空格) + 标签名**(将不做演示)

--- 
##### III. 并集选择器
同时选中各个基本选择器所选择的范围，任何形式的选择器都可以。

```
div,span,td{
	background-color: aquamarine;
}

所有符合以上标签或者选择器的内容都将使用以上格式
```

---
### 盒模型 ###
![盒模型](http://image.bubuko.com/info/201802/20180220195838534266.png)
盒模型 = content + padding(内边距) + border(边界) + margin(外边距) 

#### I. padding ####
- <font color=red>**连写顺序: 先上 - 后左右 - 再下 , 从上而下 , 顺时针**</font>
	```
	padding: 10px ;					上，右，下，左的距离为10px
	padding: 10px  20px ;				上下10px   左右20px
	padding: 10px  20px  30px ;		上10px  左右20px   下30px
	padding: 10px  20px  30px  40px ;	上， 右 ， 下， 左
	```
- 当设定当前盒子大小时,并自身设置padding，宽/高 = 	设定宽/高 + padding值；
- ** 0 ≤ 盒子的padding值 ≤ 继承外层标签的宽高范围，将不会影响该盒子大小。**
- padding值不可为负。



#### II. border ####
相关属性有:
```
	border: dashed;
	border: dashed #FF0000 1px;
	border-top: dashed #FF0000 1px;
	border-top-style: dashed;
	border-top-color: #FF0000;
	border-top-width: 1px;
	...
```
- border-width:   边框宽度
- border-style:    边框样式
	- `solid`		实线
	- `dotted`		点线
	- `dashed`		虚线
- border-color:		边框颜色

#### III. margin ####
- <font color=red>**连写顺序: 先上 - 后左右 - 再下 , 从上而下 , 顺时针**</font>
	```
	margin: 10px ;					上，右，下，左的距离为10px
	margin: 10px  20px ;				上下10px   左右20px
	margin: 10px  20px  30px ;		上10px  左右20px   下30px
	margin: 10px  20px  30px  40px ;	上， 右 ， 下， 左
	```
- **两个盒子<font color=red>垂直相邻</font>，<font color=red>外边距以二者margin的最大值为准</font>；**

---
### 附录之  `background` ###
- 属性连写：除了**固定数值参数**，其他参数没有顺序可言。

	```
	background: url(img/HBuilder.png) red repeat-x 20px 20px;
	```
- `background-color`
- `background-image`: **必须设置宽高**

	```
	width: 500px;
	height: 200px;
	background-image: url(img/HBuilder.png);
	```
- `background-repeat`

	- `repeat` （默认值）
	- `no-repeat` （不重复平铺）
	- `repeat-x` （横向重复平铺）
	- `repeat-y `（纵向重复平铺）
	<br>
- `background-position`: **背景位置的设置 , 同时设置两个固定数值参数时分别代表水平和竖直的位置 ;** 
	参数包括：固定数值，center，left，right，top，bottom , 
	
	```
	background-position: center center;
	background-position: bottom right;
	background-position: 30% 20%;
	background-position: 30px 20px;
	background-position-x: center;
	background-position-y: center;
	```
- `background-attachment` ：**是否固定背景**

	- `Scroll`（默认值）滚动 
	- `fixed` （图片固定）


	

---