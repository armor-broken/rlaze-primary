## 创建项目

`npx create-react-app 项目名称 --template typescript`

## 项目配置

### 相对路径层级太深问题

`tsconfig.json`中加入`"baseUrl": "./src",`更改项目查找绝对路径

### 统一格式化

1. 安装 prettier
   [安装地址](https://prettier.io/docs/en/install.html)

   ```
   1. 安装：yarn add --dev --exact prettier
   2. 创建prettierrc.json：echo {}> .prettierrc.json
   3. 创建.prettierignore：touch .prettierignore
   4. 手动格式化命令：yarn prettier --write . // 手动方法不建议

   ```

2. 配置 Pre-commit Hook
   [配置地址](https://prettier.io/docs/en/precommit.html)
   `npx mrm@2 lint-staged`

3. 安装 eslint-config-prettier
   > `create-react-app`创建的项目内置 ESLint 和 prettier 会有冲突

安装：`yarn add eslint-config-prettier -D`
配置：eslintConfig 中加入`prettier`

## 规范 git commit

### 配置 commitlint

[配置地址](https://github.com/conventional-changelog/commitlint#getting-started)

1. 安装：`yarn add @commitlint/{config-conventional,cli}`
2. 配置：`echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js`
3. package.json 中加入配置

```
{
  "hooks": {
    "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
  }
}
```

[commitlint 安装的 commit 规则](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional)
