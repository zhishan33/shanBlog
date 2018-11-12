---
layout: default
title: css多行文本
---

# css多行文本

## html

```

  <div class="text-wrapper">
    <div class="more-line-text">
      more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text
      more-line-text more-line-text
    </div>
  </div>

```
## CSS

```
  .text-wrapper {
    height: 40px;
    line-height: 20px;
    overflow: hidden;
  }

  .text-wrapper .more-line-text {
    float: right;
    margin-left: -5px;
    width: 100%;
    word-break: break-all;
  }

  .text-wrapper::before {
    float: left;
    width: 5px;
    content: '';
    height: 40px;
  }

  .text-wrapper::after {
    float: right;
    content: "...";
    height: 20px;
    line-height: 20px;
    /* 为三个省略号的宽度 */
    width: 3em;
    /* 使盒子不占位置 */
    margin-left: -3em;
    /* 移动省略号位置 */
    position: relative;
    left: 100%;
    top: -20px;
    padding-right: 5px;
    text-align: center;
    background: linear-gradient(to right,transparent 0%, transparent 30%,#FFF 30%, #FFF);
  }
```

## 相关链接
- [首页](http://zhishan33.github.io/shanBlog/)
- [CSS 来实现多行文字截断](https://juejin.im/post/5be2dd8fe51d451bb447e0a5?utm_source=gold_browser_extension)
> {{page.date | date_to_string}}
