---
layout: post
title: sbt快速指南
categories: scala
---

[English Version]({% post_url 2020-08-03-sbt-quick-reference %})

## sbt版本

该指南基于sbt 1.3.2. 你可以使用 `sbt sbtVersion` 命令来查看自己的sbt版本.

<!-- more -->

## 命令

### 官方指南

你可以先阅读[sbt by example](https://www.scala-sbt.org/1.x/docs/sbt-by-example.html)。这篇文章能让你快速了解sbt如何使用。

### sbt REPL

所有下面列出的命令都可以在sbt REPL中运行，在sbt REPL下运行的命令速度会更快。在工程目录的终端下启动`sbt`即可开启sbt REPL，然后在输入命令的时候去掉sbt，如`sbt run`在REPL下应只输入`run`。

### 新建一个sbt工程

```sh
sbt new scala/hello-world.g8
```

该命令会从hello-world模板中创建新的sbt工程。[在这里](https://github.com/foundweekends/giter8/wiki/giter8-templates)你可以找到可用模板列表.

### 运行sbt工程

```sh
sbt run
```

该命令会编译并运行sbt工程。

### 编译工程

```sh
sbt compile
```

该命令仅编译sbt工程。

### 监视工程中文件更改并重编译

```sh
sbt ~compile
```

### 运行测试

```sh
sbt test
```

## 设置

### 添加新的下载仓库

编辑项目文件夹中的build.sbt文件，在文件中添加两行

```
resolvers +=
  "Sonatype OSS Snapshots" at "https://oss.sonatype.org/content/repositories/snapshots"
```

添加完成后，项目中可使用名为"Sonatype OSS Snapshots"，URL为`https://oss.sonatype.org/content/repositories/snapshots`的仓库。你可以按该模板添加自己需要的仓库。添加新仓库的时候注意不要与已有仓库重名。

关于更多Resolvers的用法，请参考[sbt manual on Resolvers](https://www.scala-sbt.org/1.x/docs/Resolvers.html)文档。