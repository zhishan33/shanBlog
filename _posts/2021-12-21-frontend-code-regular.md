---
layout: default
title: ESLint + Prettier | commitizen cz-conventional-changelog | husky
date: 2020-11-07 +0800
categories:
tags: [js, notes]
---

## 代码风格 | 提交规范 | 提交验证

## 代码风格

### ESLint

```js
npm i eslint -D
eslint --init

{
  "rules": {
    "quotes": ["error", "double"]
  }
}
```

  1. quotes 表示引号规范，是众多规范中的一个，它的值是一个数组。数组第一项是错误级别，是以下 3 个值之一，数组第二项才是真正的规范
    - "off" or 0 - 关闭规范
    - "warn" or 1 - 警告级别规范
    - "error" or 2 - 错误级别规范
  
### Prettier 配置文件和上面 ESLint 下的 rules 配置作用一致

```js
npm i prettier -D

{
  "singleQuote": true, // 是否单引号
  "semi": false, // 声明结尾使用分号(默认true)
  "printWidth": 100, // 一行的字符数，超过会换行（默认80）
  "tabWidth": 2, // 每个tab相当于多少个空格（默认2）
  "useTabs": true, // 是否使用tab进行缩进（默认false）
  "trailingComma": "all", // 多行使用拖尾逗号（默认none）
  "bracketSpacing": true, // 对象字面量的大括号间使用空格（默认true）
  "jsxBracketSameLine": false, // 多行JSX中的>放置在最后一行的结尾，而不是另起一行（默认false）
  "arrowParens": "avoid" // 只有一个参数的箭头函数的参数是否带圆括号（默认avoid）
}

```

## 提交规范 (可以用 git cz 命令来代替 git commit 命令)

### commit 规范

```js
npm i -g commitizen cz-conventional-changelog

```

1. 创建 ~/.czrc 文件，写入如下内容：

```text
{ "path": "cz-conventional-changelog" }
```

## 提交验证

### husky

```js
npm i husky -D

{
  "scripts": {
    "prepare": "husky install"
  }
}

npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'

npm i @commitlint/{config-conventional,cli} -D
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```
