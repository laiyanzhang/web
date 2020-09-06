# CSS

标签（空格分隔）： CSS

---

## 1.选择器优先顺序
- 内联样式 > id 选择器 > 类选择器 = 伪类选择器 = 属性选择器 > 标签选择器 = 伪元素选择器
!important规则除外，优先级最高

## 2.链接
- .link、.visited、.hover、.active
- a:hover 必须跟在 a:link 和 a:visited后面
a:active 必须跟在 a:hover后面

## 3.对齐
- 文字水平对齐：text-align:center
- 文字垂直对齐：vertical-align:middle(表格td)
- 元素对齐
  - 水平居中对齐：设置width以及margin：auto
  - 左右对齐：
    position：absolute
    float：right/left
  - 垂直居中对齐：
    padding（对半分）
    line-height=height
    position:absolute + top:50% + left:50% + transform:translate(-50%,-50%)
    vertical-align:middle：
     - 父元素内两个子元素，两个子元素均为inline-block，一个子元素设置height:100%,width:0作为父元素基线，一个子元素设置vertical-align:middle即可实现该元素居中


## 4.盒子模型
- margin、outline(不占用weight与height)、border、padding、content
- box-sizing:
  - content-box:width仅包括content
  - border-box:width包括content、padding、border
- flex-box
  - display:flex/-webkit-flex
  - direction:rtl(弹性盒子元素排列顺序)
  - flex-direction:row/colunmn(列与行)
  - justify-content:弹性项横轴对齐方式
  - align-items:弹性项纵轴对齐方式
  - flex-wrap:换行方式
  - align-content：换行时的align-items
  - 弹性子元素属性：order顺序、margin:auto居中、flex:扩大缩小比率

## 5.属性顺序
- 上右下左、上（左右）下、（上下）（左右）

## 6.显示与隐藏
- display：隐藏后不占用原来空间
- visibility：隐藏后仍然占用空间
- display属性：
  - block：独占一行，盒子模型均可控制
  - inline：和相邻元素在同一行，盒子模型(除左右内外边距)不可控制
  - inline-block：同行显示但可修改属性

## 7.position
- static：默认值，不受top、bottom、left、right
- fixed：固定位置，与文档流无关，不占据空间
- relative：相对正常位置移动，但原本占据空间不变
- absolute：相对于最近已定位的父元素,如果没有则相对于<html>,与文档流无关，不占据空间
- sticky:跨越阈值前相对定位，跨越后固定定位
- z-index：当出现重叠元素时可以设置堆叠顺序，定位盒子>浮动盒子>标准盒子，当为负数时低于浮动盒子与标准盒子

## 8.媒体类型
- @media screen/print(屏幕和打印的不同样式)

## 9.响应式
- 根据屏幕大小产生不同显示
- @media (max-width:600px)屏幕小于600px则适用

## 10.背景
- background-origin:背景图像的位置区域
  - content-box
  - padding-box
  - border-box
- background-clip:背景的绘制区域
  - content-box
  - padding-box
  - border-box

## 11.渐变
- 线性渐变：默认自上而下，可以设置
 background-image: linear-gradient(angle, color-stop1, color-stop2);角度顺时针变化，正北方为0deg
- 径向渐变：
  background-image: radial-gradient(shape size at position, start-color, ..., last-color);

## 12.文本效果
- text-shadow/box-shadow/text-overflow/word-wrap/word-break

## 13.动画转换
- transform：x轴向右，y轴向下（2D)
  - translate(x,y)移动
  - rotate(r deg)旋转
  - scale(w,h)宽度高度的倍数变化
  - skew(x deg, y deg)水平垂直方向倾斜
- transform：（3D）
  - rotateX/Y(r deg)均从控件左侧向下旋转
- transition:property duration[ function delay]（过渡）
- animation:name duration
  - 动画定义：@keyframes name { from{} , to{} / percent{} }

      



