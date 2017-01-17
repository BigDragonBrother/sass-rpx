# Rpx

> Fork from: https://github.com/pierreburel/sass-rem

微信小程序用于 `px` 转换成 `rpx` 单位的 Sass 混入类/函数。

(大坑未更新)

演示: [Sassmeister](http://www.sassmeister.com/gist/a5820008884df7e255ef5715768d5af7) / [Codepen](http://codepen.io/pierreburel/pen/ogGzgX)

适用于: [Sass](https://github.com/sass/sass) 3.2+ (3.3+ for maps)

查看: https://github.com/pierreburel/sass-rem / https://github.com/pierreburel/sass-em

---

## 安装

Download [`_rpx.scss`](https://raw.githubusercontent.com/peckzeg/sass-rpx/master/_rpx.scss)

---

## 食用指南

导入 `_rpx.scss`, 设置设计稿所使用的类型 `$rpx-base-draft` 然后开始使用 `rpx` 混入或函数。

### SCSS

```scss
@import "rpx";

h1 {
  @include rpx(font-size, 24px); // Simple
  @include rpx(border-bottom, 1px solid black); // Shorthand
  @include rpx(box-shadow, 0 0 2px #ccc, inset 0 0 5px #eee); // Multiple values
  text-shadow: rpx(1px 1px #eee, -1px -1px #eee); // Function and multiple values
  // List support (Sass 3.3+)
  @include rpx((
    margin: 20px 1px,
    padding: 10px
  ));
}
```

### CSS

```css
h1 {
  font-size: 48rpx;
  border-bottom: 2rpx solid black;
  box-shadow: 0 0 4rpx #ccc, inset 0 0 10rpx #eee;
  text-shadow: 2rpx 2rpx #eee, -2rpx -2rpx #eee;
  margin: 40rpx 2rpx;
  padding: 20rpx;
}
```

---

## 改变设计稿类型

默认下，sass-rpx 使用 `iphone6` 作为设计稿类型（更多类型可参照 [微信公众平台 | 小程序 - 框架 - WXSS - 尺寸单位](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxss.html?t=2017112)）。

当然，你可以通过改变 `$rpx-base-draft` 来修改该值。

### SCSS

```scss
@import "rpx";

$rpx-base-draft: iphone6 plus;

h1 {
  @include rpx((
    font-size: 24px,
    margin: 10px 1rpx
  ));
}
```

### CSS

```css
h1 {
  font-size: 48rpx;
  margin: 20rpx 1rpx;
}
```
