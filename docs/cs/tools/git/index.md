---
title: "Git"
---

## Github commit 规范

### 格式 Format

每次提交，Commit message 都包括三个部分：**Header**，**Body** 和 **Footer**。其中，**Header** 是必需的，**Body** 和 **Footer** 可以省略。

```text
<type>(<scope>): <subject>
<空行>
<body>
<空行>
<footer>
```

不管是哪一个部分，任何一行都不得超过72个字符（或100个字符）。Header 部分只有一行，包括三个字段：`type`（必需）、`scope`（可选）和 `subject`（必需）。Footer 部分如果提交存在一个与之关联的 Issue 则要关联。

示例：

```text
docs(changelog): update changelog to beta.5
```

```text
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, 
and users need the latest of these.
```

### 主题 Subject

subject 是本次 commit 目的的简短描述，一般不要超过50个字符：

* **使用祈使句和现在时**：例如使用 "change" 而不是 "changed" 或 "changes"。
* **规范大小写和相应书写规则。**
* **无需加句号符标识结尾。**

### 类型 Type

类型是描述当前提交性质的枚举类型，含有以下的枚举值:

* **build**: Changes that affect the build system or external dependencies \(example scopes: gulp, broccoli, npm\)
* **ci**: Changes to our CI configuration files and scripts \(example scopes: Travis, Circle, BrowserStack, SauceLabs\)
* **docs**: 仅修改文档相关，比如 README, CHANGELOG, CONTRIBUTE等等
* **feat**: 特性增加
* **fix**: 异常 bug 修复
* **perf**: 性能优化，比如提升性能、体验
* **refactor**: 代码重构，没有加新功能或者修复 bug
* **style**: 不影响代码含义的改动 \(white-space, formatting, missing semi-colons, etc\)，仅仅修改了空格、格式缩进、逗号等等，不改变代码逻辑
* **test**: 对测试的增加或修复，包括单元测试、集成测试等
* **merge**: 分支合并（格式 -&gt; `orgin_branch into target_branch` ）

如果type为feat和fix，则该 commit 将肯定出现在 Change log 之中。其他情况（docs、chore、style、refactor、test）由你决定，要不要放入 Change log，建议是不要。

* **chore**: 改变构建流程、或者增加依赖库、工具等
* **revert**: 回滚到上一个版本

### 作用域 Scope

scope 用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同，同样属于枚举类型。

通用的有：

* **$git**
* **$script**
* **$\*-script**
* **$npm**
* 等等

例如，Egg 项目：

* **$router**
* **$controller**
* **$srv**
* **$test**
* $**schedule**
* **$db**
* **$config**
* **$\*-config** \[ \* -&gt; webpack、eslint \]
* **$logger**
* 等等

其它常见的有：

* **$cmpt**
* **$container**
* **$view**
* **$api**
* 等等

### 主体 Body

Body是对本地提交的一个详细描述，需要注意的是，描述每行字符不应超过 72 个字符，这利于各种环境下良好的阅读体验。

## 参考资料

* [Git Commit 规范](https://feflowjs.com/zh/guide/rule-git-commit.html)
* [Git Commit 规范](https://github.com/o-w-o/way/blob/master/appendixs/wiki/git-commit.md)
