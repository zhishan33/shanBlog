---
layout: default
title: git hooks
date: 2021-07-19 +0800
categories:
tags: [git, note]
---

## pre-commit

1. 将husky添加到项目的开发依赖中
npm install -D husky

2. 在packgae.json中添加prepare脚本

```json
{
  "scripts": {
    "prepare": "husky install"
  }
}
```

3. 添加git hooks，运行一下命令创建git hooks

npx husky add .husky/pre-commit "npm run test"

## commit-msg

1. npm install --save-dev @commitlint/config-conventional @commitlint/cli
2. 新建文件commitlint.config.js
3. 添加代码

```js
module.exports = {
  extends: ["@commitlint/config-conventional"],
  rules: {
    "type-enum": [
      2,
      "always",
      [
        "build",
        "bug", // 此项特别针对bug号，用于向测试反馈bug列表的bug修改情况
        "feat", // 新功能（feat）
        "fix", // 修补bug
        "docs", // 文档（documentation）
        "style", // 格式（不影响代码运行的变动）
        "refactor", // 重构（即不是新增功能，也不是修改bug的代码变动）
        "test", // 增加测试
        "chore", // 构建过程或辅助工具的变动
        "revert", // feat(pencil): add ‘graphiteWidth’ option (撤销之前的commit)
        "merge" // 合并分支， 例如： merge（前端页面）： feature-xxxx修改线程地址
      ]
    ]
  }
};

```

4. npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'


## 相关链接

- [首页](https://zhishan33.github.io/shanBlog/)
- [husky使用总结](https://zhuanlan.zhihu.com/p/366786798)
- [@commitlint/config-conventional](https://zhuanlan.zhihu.com/p/366786798https://www.npmjs.com/package/@commitlint/config-conventional)

> {{page.date | date: '%Y, %b %d'}}
