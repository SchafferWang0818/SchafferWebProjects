# 前端基础之CSS / CSS3 样式属性 #

<br>
## 1. background ##
- 无论背景颜色和图片都必须设置水平和竖直的位置。其他无顺序可言。

`background-repeat`|属性含义
-|-
`repeat` 		|	默认值
`no-repeat` 	|	不重复平铺
`repeat-x` 	|	横向重复平铺
`repeat-y `	|	纵向重复平铺

`background-attachment` |属性含义
-|-
`Scroll`|	默认值，**随滚动条滚动 **
`fixed` |	不随滚动条滚动
- 属性连写<br>
	```
	background: url(img/HBuilder.png) red repeat-x 20px 20px;
	```
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
---
## 2. text ##
属性				|	描述
				:-	|	:-
`color`				|	文本颜色。
`direction`			|	文本方向。
**`line-height`**		|	文本行高。
**`letter-spacing`**	|	字符/字的间距。
**`word-spacing`**	|	单词/字间距，**仅在有空格的情况生效**。
`text-align`			|	文本对齐。左，中，右。
`text-decoration`		|	文本修饰（线）。
`text-indent`			|	文本首行缩进，可正可负。CSS2.1 之前可继承。
`text-shadow`			|	文本阴影颜色。CSS2 包含该属性，CSS2.1 没有保留该属性。
`text-transform`		|	文本大小写转换。
`white-space`			|	文本空白处理，查看以下表格。
`font-family`			|	字体，**多个字体名称用于向后逐个兼容**


`text-transform`	|	含义
			:-	|	:-
`none`			|	不做任何改动
`uppercase`		|	全大写
`lowercase`		|	全小写
`capitalize`		|	每个单词的首字母大写，**仅在有空格的情况生效**。

`white-space`值	|	空格	|	换行	|	自动换行
			:-	|	----		|	----		|	-
`normal`			|	合并	|	忽略	|	允许
`nowrap`		|	合并	|	忽略	|	不允许
`pre`			|	保留	|	保留	|	不允许
`pre-wrap`		|	保留	|	保留	|	允许
**`pre-line`**	|	合并	|	保留	|	允许

---





---
## 列表list ##
主要设置列表前方的标志。

属性				|	描述
				-	|	-
`list-style	`			|	属性连写
`list-style-image`		|	将图象设置为列表项标志。`url(../../.../1.jpg)`
`list-style-position`	|	设置列表中列表项标志的位置 ( inside 偏内侧 、outside 偏外侧)
**`list-style-type`**	|	设置列表项标志的类型。


`list-style-type`值		|	描述
				-	|	-
none				|	无序：无标记。
disc					|	无序：默认实心圆。
circle				|	无序：空心圆。
square				|	无序：实心方块。
decimal				|	有序：数字。
decimal-leading-zero	|	有序：0开头的数字标记。(01, 02, 03, 等。)
lower-roman			|	有序：小写罗马数字(i, ii, iii, iv, v, 等。)
upper-roman			|	有序：大写罗马数字(I, II, III, IV, V, 等。)
lower-alpha			|	有序：小写英文字母The marker is lower-alpha (a,b, c, d, e, 等。)
upper-alpha			|	有序：大写英文字母The marker is upper-alpha (A, B, C, D, E, 等。)
lower-greek			|	有序：希腊字母(α, β, γ, 等。)
lower-latin			|	有序：小写拉丁字母(a, b, c, d, e, 等。)
upper-latin			|	有序：大写拉丁字母(A, B, C, D, E, 等。)
hebrew				|	有序：传统的希伯来编号方式
armenian			|	有序：传统的亚美尼亚编号方式
...					|	...

---
## 表格 table、tr、th、td ##
- **默认table及table的所有子元素都有边框border但宽度为0。**
- 文字对齐方式`text-align`,`vertical-align`

属性				|	描述
			:-		|	:-
`visibility`			|	**应用于行是否可见**<br>`visibility : collapse`不可见，收缩空间<br>`visibility : hidden` 不可见，保留空间<br>`visibility : visible` 可见 
**`border-collapse`**	|	**设置是否把表格边框合并为单一的边框。<br> `= collapse` 合并内外部边框；<br> `= separate` 显示内外部边框；**
**`text-align`**		|	文字**左、中、右**对齐
**`vertical-align`**	|	文字**上、中、下**对齐
**`border-spacing`**	|	**单元格边框的距离**
**`caption-side`	**	|	**设置表格标题的位置，与`<caption></caption>`一起使用。**
`empty-cells`			|	设置是否显示表格中的空单元格。<br> `= hide` 隐藏空的单元格；<br> `= show` 显示空的单元格；
`table-layout`			|	设置显示单元、行和列的算法。
---
## 动作变换(transform) ##

### 旋转(rotate) ###
```
transform:rotate(30deg);
-ms-transform:rotate(30deg); /* IE 9 */
-moz-transform:rotate(30deg); /* Firefox */
-webkit-transform:rotate(30deg); /* Safari and Chrome */
-o-transform:rotate(30deg); /* Opera */
```
---