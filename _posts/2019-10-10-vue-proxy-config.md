---
layout: default
title: vue proxy config
date: 2019-10-10 +0800
categories: vue
tags: [vue, proxy, config]
---

## vue proxy config

```js
module.exports = {
	devServer: {
		// proxy: {
		//   '/api': {
		//     target: "http://refund1.domain.vip/",
		//     changeOrigin: true,
		//     pathRewrite: {
		//       '^/api': ''
		//     }
		//   }
		// }
		proxy: {
			'/ng': {
				target: "http://refund1.domain.vip/",
				changeOrigin: true,
				pathRewrite: {
					'^/ng': 'ng'
				}
			},
			'/refund': {
				target: "http://refund1.domain.vip/",
				changeOrigin: true,
				pathRewrite: {
					'^/refund': 'refund'
				}
			}
		}
	}
}
// package.json
// ,
//   "vue": {
//     "devServer": {
//       "proxy": {
//         "/api" : {
//           "target": "http://refund1.zikaoshu.vip/",
//           "changeOrigin": true,
//           "pathRewrite": {
//             "^/api": ""
//           }
//         }
//       }
//     }
//   }
```

### API

```JS
const baseUrlServer = `http://${ENV}.domain.vip`; //测试环境
// const baseUrlLocal = `/api`; //本地代理
const baseUrlLocal = ``; //本地代理
const baseUrl = process.env.NODE_ENV === 'development' ? `${baseUrlLocal}` : `${baseUrlServer}`;
// const baseUrl = `${baseUrlServer}`;
const API = {
	getB: baseUrl + '/refund/B1',
	LOGIN: baseUrl + '/ng/refund/refund/login', //用户授权，获取个人信息。
	ISALLOWAPPLYREFUND: baseUrl + '/ng/refund/refund/isAllowApplyRefund', //押题退款申请时间和资格判断
	GETEXAMINATIONORDERINFO: baseUrl + '/ng/refund/refund/getExaminationOrderInfo', // 查询用户当前考期押题订单信息
	UPLOADUSERGRADEIMG: baseUrl + '/refund/uploadUserGradeImg', //上传截图
	GETMYREFUNDINFO: baseUrl + '/ng/refund/refund/getMyRefundInfo', //查询用户退款申请记录详情信息
	GETPAGEREFUNDINFO: baseUrl + '/ng/refund/refund/getPageRefundInfo', //分页查询用户退款申请记录信息
	ADDUSERREFUND: baseUrl + '/ng/refund/refund/addUserRefund', //新增一个用户退款申请记录
	CANCELUSERREFUND: baseUrl + '/ng/refund/refund/cancelUserRefund', //撤销押题退款申请
	UPDATEUSERREFUNDINFO: baseUrl + '/ng/refund/refund/updateUserRefundInfo', //修改押题退款申请
}
```

## 相关链接
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
