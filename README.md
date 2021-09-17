# vue-demo

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

# Git  提交代码规范

## git  创建分支规范

格式：[type]*name_date*功能描述  
例如：feature_yjr_20201001_user-manage

**type 如下**

- feature：功能开发分支
- hotfix：用来修复 bug

## git  常用的分支

- **Master  分支**
  最近发布到生产环境的稳定代码，  这个分支只能从【Pre-production】分支合并。改 bug 和开发新需求全部从【Master】新拉分支
- **Pre-production 分支**
  用于发布生产环境的分支。从【Test】分支合并，稳定后合并到【Master】分支
- **Test 分支**
  用于提测的分支。各开发分支提【Dev】联调无误后，由各开发分支合并到【Test】进行测试。 测试确定可发版后合并到【Pre-production】分支
- **Dev  分支**
  主开发分支。从各开发分支合并而来，前后端功能联调。

---

**上面四个是受保护分支，所有开发人员均不在这几个分支直接开发**

- **各 Hotfix 分支**
  当我们在 Production 发现新的 Bug 时候，我们需要从【Master】创建一个 Hotfix,  完成 Hotfix 后，我们合并到【Pre-production】和【Dev】分支
- **各 Feature 分支**
  各开发人员负责的功能开发分支。分支功能开发完及自测完以后合到【Dev】分支前后端联调

## git  提交信息规范

每次提交，Commit message  都包括三个部分：Header，Body  和  Footer。
其中，Header  是必需的，Body  和  Footer  可以省略。

```js
<type>(<scope>): <subject>
// 空一行
<body>
// 空一行
<footer>
```

不管是哪一个部分，任何一行都不得超过 72 个字符（或 100 个字符）。这是为了避免自动换行影响美观。  
**Header**  
  Header  部分只有一行，包括三个字段：type（必需）、scope（可选）和 subject（必需）。  
**type**（必需）  
  Type 用于说明  commit  的类别，只允许使用下面 8 个标识。

- feat：新功能（feature）
- fix：修补 bug
- docs：文档（documentation）
- style：  格式（不影响代码运行的变动）
- refactor：重构（即不是新增功能，也不是修改 bug 的代码变动）
- test：增加测试
- chore：构建过程或辅助工具的变动,非 src 或者 测试文件的更新
- up: 不属于上述分类时，可使用此类别

**scope**（可选）  
  Scope 用于说明  commit  影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同。  
**subject**（必需）  
  Subject 是  commit  目的的简短描述，不超过 50 个字符。用汉字即可，明确清晰。  
**例子**  
`【feat】策划管理-页面布局`  
`【fix】登陆-验证码失效问题`
