# CSS

## Import

```html
<link rel="stylesheet" type="text/css" href="style.css" />
```

## Display

### none

元素不会被显示

### block

**块级元素**独占一行。
常见的块元素有：`p`、`h1`、`h2`、`h3`、`br`、`div`等。

### inline

**内联元素**只占自身的宽度。
常见的内联元素有：`a`、`span`等。

### inline-block

**行内块元素**既能设置宽高，也不会独占一行。
常见的行内块元素有：`img`、`iframe`等。

### table/inline-table

- table-caption: `caption`
- table-header-group: `thead`
- table-row-group: `tbody`
- table-row: `tr`
- table-cell: `th`、`td`

### inherit

继承自父元素

## Hidden

```css
{
    /* 方法1：不占据页面空间 */
    display: none;

    /* 方法2：占据页面空间，无法点击 */
    visibility: hidden;
    /* visibility: visible; */

    /* 方法3：占据页面空间，可以点击 */
    opacity: 0;
    /* opacity: 1; */
}
```

## Selector

### Basic

- `tag_name {}`：标签选择器
- `.cls_name {}`：类选择器
- `#id_name {}`：ID选择器
- `* {}`：通配选择器

### Advanced

- `selector1,selector2 {}`：并集选择器
- `selector2selector2 {}`：交集选择器（若有标签选择器，则必须为第一个）
- `selector2:not(selector2) {}`：排除选择器
- `selector1+selector2 {}`：兄弟选择器（后一个紧挨的平级标签）
- `selector1~selector2 {}`：兄弟选择器（后边所有的平级标签）
- `selector1 selector2 {}`：后代选择器（后代的后代也可被选中）
- `selector1>selector2 {}`：子元素选择器（必须为直系）

### Pseudo-class

- `a:link {}`：未访问过的链接
- `a:visited {}`：访问过的链接，只能设置字体颜色
- `selector:hover {}`：鼠标悬停时样式
- `selector:active {}`：鼠标点击时样式
- `input:focus {}`：文本框获得焦点时样式
- `selector::selection {}`：（Chrome）选中的文字样式
- `selector::-moz-selection {}`：（Firefox）选中的文字样式
- `selector:first-child {}`：（当前容器内）第一个子元素
- `selector:last-child {}`：（当前容器内）最后一个子元素
- `selector:nth-child(n) {}`：（当前容器内）第n个子元素
- `selector:nth-child(even) {}`：（当前容器内）偶数位置
- `selector:nth-child(odd) {}`：（当前容器内）奇数位置
- `selector:first-of-type {}`：第一个元素
- `selector:last-of-type {}`：最后一个元素
- `selector:nth-of-type {}`：第n个元素

### Pseudo-element

- `p:first-letter {}`：首字母样式
- `p:first-line {}`：首行样式
- `p:before {content:"[前]";color:red;}`：每行之前，添加内容
- `p:after {content:"[后]";color:orange;}`：每行之后，添加内容

### Attribute

- `selector[attr] {}`：选取含有指定属性的元素
- `selector[attr1][attr2] {}`：同时含有属性attr1和attr2的元素
- `selector[attr="value"] {}`：含有指定属性且值为value的元素
- `selector[attr|="value"] {}`：含有指定属性且值为value或值以value开头的元素
- `selector[attr^="head"] {}`：含有指定属性且值以head开头的元素
- `selector[attr$="tail"] {}`：含有指定属性且值以tail结尾的元素
- `selector[attr*="content"] {}`：含有指定属性且值包含content的元素
- `selector[attr~="content"] {}`：含有指定属性且值以空格断句时可出现content的元素

## Unit of length

### Absolute

| Value  | Explain |
| :- | :-: |
| px | 像素
| cm | 厘米
| mm | 毫米
| in | 英寸

### Relative

| Value  | Explain |
| :-  | :-: |
| %   | 100% = 包含块的高或宽
| em  | 1 em = 1 当前元素的 font-size
| rem | 1 rem = 1 根元素的 font-size

## Font

```css
{
    /* 字体类型： Serif | Sans-serif | Monospace | Cursive | Fantasy */
    font-family: Serif;
    /* 可用逗号同时指定多个字体类型 */

    /* 字体风格： normal | italic:斜体 | oblique:倾斜 */
    font-style: normal;

    /* 字体变形： normal | small-caps:小型大写字母 */
    font-variant: normal;

    /* 字体加粗： normal | bold | <number:[100, 900]>:加粗等级 */
    font-weight: normal;

    /* 字体大小： 长度单位 */
    font-size: 100%;

    /* 简写 */
    /* font: style family; */
    /* font: style weight size family; */
}
```

## Box

![](images/box.png)

- padding: 内边距
  - `padding: top right bottom left;`
- border: 边框
  - `border: width style color`
  - `border-width: top right bottom left`
  - `border-style: top right bottom left`
  - `border-color: top right bottom left`
- margin: 外边距
  - `margin: top right bottom left;`

## Border Style

| Value   | Effect |
| :-:     | :-: |
| none	  | 无边框
| hidden  |	无边框，用于解决`table`边框冲突
| dotted  |	点状
| dashed  |	虚线
| solid	  | 实线。
| double  |	双线
| groove  |	3D 凹槽
| ridge	  | 3D 垄状
| inset	  | 3D inset
| outset  |	3D outset
| inherit |	从父元素继承边框样式。

### 缩写规则

![](images/trbl.png)

### [Vertical outside margin fold](vertical_outside_margin_fold.html)

- 垂直外边距折叠

### [Overflow](overflow.html)

- 内容溢出

### Clearfix

解决浮动布局高度塌陷和外边界传递（兼容IE6）

```css
.clearfix {zoom: 1}
.clearfix:before, .clearfix:after {
    content: '';
    display: table;
    clear: both;
}
```

## Layout

### [Float](float.html)

- 浮动布局

### [Flex](flex.html)

#### 容器属性

```css
{
    /* 主轴方向: 左右水平(默认) | 右左水平 | 上下垂直 | 下上垂直 */
    flex-direction: row | row-reverse | column | column-reverse;

    /* 一行排不下时如何换行: 不换行（默认） | 换行，第一行在上方 | 换行，第一行在下方 */
    flex-wrap: nowrap | wrap | wrap-reverse;

    /* 缩写 <flex-direction> <flex-wrap> */
    /* flex-flow: <flex-direction> <flex-wrap>; */

    /* 水平如何对齐: 左（默认） | 右 | 中 | 两端 | 假两端 */
    justify-content: flex-start | flex-end | center | space-between | space-around;

    /* 垂直如何对齐: 头 | 尾 | 中心轴 | 文本低端 | 占满高度（默认） */
    align-items: flex-start | flex-end | center | baseline | stretch;

    /* 多轴对齐: 双轴起点 | 双轴终点 | 居中 |　两端 | 假两端 | 占满交叉轴（默认） */
    align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

- justify-content
  - ![](images/justify-content.png)
- align-items
  - ![](images/align-items.png)
- align-content
  - ![](images/align-content.png)

#### 子对象属性

```css
{
    /* 项目排列顺序，顺序越小越靠前 */
    order: <integer>;

    /* 项目的放大比例，默认为0 */
    flex-grow: <number>;

    /* 项目的缩小比例，默认为1 */
    flex-shrink: <number>;

    /* 在分配多余空间之前，项目占据的主轴空间 */
    flex-basis: <length> | auto;

    /* 缩写 <flex-grow> <flex-shrink> <flex-basis> */
    flex: 0 1 auto;

    /* 允许单个对象有与其他对象不一样的对齐方式 */
    align-self: auto | flex-start | flex-end | center | baseline | stretch;
}
```