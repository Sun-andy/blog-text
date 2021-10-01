# css知识总结

## 一、浏览器渲染原理

1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树（CSSOM）
3. 将两棵树合并成一颗渲染树（render tree）
4. Layout布局（文档流、盒模型、计算大小和位置）
5. Paint绘制（把边框颜色、文字颜色、阴影等画出来）
6. Composite合成（根据层叠关系展示图画）


## 二、CSS动画的两种做法

<h2>动画</h2>

动画是指由许多帧静止的画面，以一定的速度（如每秒16张）连续播放时，肉眼因视觉残象产生错觉，而误以为画面活动的作品。

<h2>CSS动画</h2>

与动画相似，给元素一个start位置和一个end位置，将中间移动的过程展现出来，肉眼产生错觉，误以为画面活动。

一般我们使用Transform和Animation属性来使的画面活动起来。

<h2>Transform</h2>

CSS中的transform属性可以完成旋转，缩放，倾斜或平移给定元素。这是通过修改CSS视觉格式化模型的坐标空间来实现的。

下面介绍几种常用的属性：
* translate位移
* scale缩放
* rotate旋转
* skew倾斜

但是transform标签只是给元素一个最终的样子，无法展现出过程，通常我们需要配合transition过渡标签配合使用。


<h2>transition</h2>

作用：补充中间帧

语法：
```
transition:属性名 时长 过渡方式 延迟
```
* transition:left 200ms linear
* 可以用逗号分隔两个不同属性
* transition:left 200ms,top 400ms
* 可以用all代表所有属性
* transition:all 200ms
* 过渡方式有：linear/ease等



<h2>animation</h2>

Animation属性用来指定一组或多组动画，每组之间用逗号相隔。 下面介绍集中常见属性

```
animation: 时长 过渡方式 延迟 次数 方向 填充模式 是否暂停 动画名
```
* 时长：1s 或者1000ms
* 过渡方式： 跟transition取值一样，如linear
* 次数：3 或者infinite
* 方向：reverse/alternate/alternate-reverse
* 填充模式：none/forwards/backwards/both 
* 是否暂停：paused/running
* 以上属性都有对应的单独属性

<h2>@keyframes</h2>

关键帧 @keyframes at-rule 规则通过在动画序列中定义关键帧（或waypoints）的样式来控制CSS动画序列中的中间步骤。和 转换 transition 相比，关键帧 keyframes 可以控制动画序列的中间步骤。
```
@keyframes slidein {
  from {
    transform: translateX(0%); 
  }

  to {
    transform: translateX(100%);
  }
}

```
or
```
@keyframes slidein {
  0% {
    transform: translateX(0%); 
  }

  50% {
    transform: translateX(50%);
  }
   100% {
    transform: translateX(100%);
  }
}

```
这是用transition和animation两种方法制作的跳动的心，链接如下：

transition制作链接：http://js.jirengu.com/hinomezero/2/watch?html,css,output

animation制作链接：http://js.jirengu.com/rusudozona/1/watch?html,css,output

