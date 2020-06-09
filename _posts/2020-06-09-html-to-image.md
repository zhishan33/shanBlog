---
layout: default
title: html dataurl 互转
date: 2020-06-09 +0800
categories:
tags: [html, canvas, dataUrl, notes]
---

## 图片与 dataUrl 相互转换

### 使用 canvas 将图片转成 dataUrl (html2canvas)

```js
      html2canvas(element, {
        // allowTaint: false,
        useCORS: true
        // width: element.clientWidth,
        // height: element.clientHeight
        // dpi: window.devicePixelRatio * 2,
      })
        .then(canvas => {
          // canvas
          if (this.$store.state.common.ISDEBUG) {
            console.log("canvas:");
            console.log(canvas);
          }
          let dataUrl = canvas.toDataURL(
            "image/png"
          );
          this.imgList[this.imgList.length - 1].content = dataUrl
          // this.cardImg[index + ""] = canvas.toDataURL("image/png");

          // this.shapeImg = canvas.toDataURL("image/png");
          this._compressAndUploadFile({
            content:dataUrl,
            file:this.dataURLtoFile(
              canvas.toDataURL("image/png"),
              this.lastFile.file.name
            )
          }
          );
        })
        .catch(err => {
          if (this.$store.state.common.ISDEBUG) {
            console.log("err:");
            console.log(err);
          }
        });
    },
```

### dataUrl 转文件

```js
    dataURLtoFile(dataurl, filename) {
      console.log("dataURLtoFile");
      var arr = dataurl.split(","),
        mime = arr[0].match(/:(.*?);/)[1],
        bstr = atob(arr[1]),
        n = bstr.length,
        u8arr = new Uint8Array(n);
      while (n--) {
        u8arr[n] = bstr.charCodeAt(n);
      }
      return new File([u8arr], filename, { type: mime });
    },
```

## 相关链接

- [首页](https://zhishan33.github.io/shanBlog/)
- [html2canvas](http://html2canvas.hertzen.com/)

> {{page.date | date: '%Y, %b %d' }}
