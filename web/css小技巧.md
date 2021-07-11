### 居中

#### 水平居中

1. 如果是行内元素。给其父元素设置 text-align:center
2. 如果是块级元素。margin:0 auto;
3. 如果子元素包含 float:left 属性。为了让子元素水平居中，让父元素的宽度设置为 fix-content，并配合 margin 实现居中
4. flex2012 布局实现水平居中
   父元素可以通过

```css
.child {
  display: flex;
  justify-content: center;
}
```

5. 使用绝对定位：

```css
.son {
  position: absolute;
  width: 固定;
  left: 0;
  right: 0;
  margin: 0 auto;
}
```

#### 垂直居中

1. 可用 vertical-align 属性, 而 vertical-align 只有在父层为 td 或者 th 时, 才会生效, 对于其他块级元素, 例如 div、p 等, 默认情况是不支持的. 为了使用 vertical-align, 我们需要设置父元素 display:table, 子元素 display:table-cell;vertical-align:middle;

2. 设置父元素相对定位(position:relative), 子元素如下 css 样式:
   .son{
   position:absolute;
   height:固定;
   top:0;
   bottom:0;
   margin:auto 0;
   }
3. flex 布局居中 父级 display:flex, align-item:center;
