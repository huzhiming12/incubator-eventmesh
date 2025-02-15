
# 怎么做贡献

如果你是一个想为 eventmesh 社区做贡献的新贡献者，请阅读本文件，它描述了如何为社区做贡献，如果你在文档中发现任何问题，欢迎留下评论或建议。

## 准备工作

### 开发环境

- 您应该在您的开发环境中安装JDK。

### 代码风格

将[EventMesh CheckStyle](https://github.com/apache/incubator-eventmesh/blob/master/style/checkStyle.xml) 文件导入到你的IDEA。

对于IDEA，你可以通过以下方式导入检查样式文件:
```shell
    Editor -> Code Style -> Java -> Scheme -> Import Scheme -> CheckStyle Configuration
```

如果您在导入方案下看不到CheckStyle配置部分，您可以先安装CheckStyle-IDEA插件，就可以看到它。

您也可以使用`./gradlew check`来检查代码风格。
(注意：这个命令将检查项目中的所有文件，当你提交一个项目时，CI将只检查这个项目中被修改的文件）。

### 工作流程

以下是贡献者提交代码的工作流程:

1. 将源仓库的项目eventmesh fork到自己仓库当中

2. 克隆fork到本地存储库，就是将自己仓库的eventmesh克隆到本地
```git
git clone git@github.com:yourgithub/incubator-eventmesh.git
```

3. 创建一个新的分支进行工作
```git
git checkout -b fix_patch_xx
```

4. 让您的分支保持同步
```git
git remote add upstream git@github.com:apache/incubator-eventmesh.git
git fetch upstream master:upstream_master
git rebase upstream_master
```

5. 提交你的修改（确保你的提交信息简洁明了）

6. 推送你的提交到你的fork仓库，将修改先推送到自己的仓库

7. 创建一个pull请求

## 解释

原始仓库：https://github.com/apache/incubator-eventmesh Eventmesh的apache仓库在文中被称为原始仓库。

fork库: 从 https://github.com/apache/eventmesh fork到你自己的个人仓库，成为一个fork库。

因此，将原EventMesh仓库分叉到你自己的仓库中。

## 开发分支

**Eventmesh 当前的开发分支是 master。请向该分支提交 PR。**

- 我们建议你在你的存储库中创建一个新的开发分支，并将该分支提交给 eventmesh 的 master分支。

## 贡献类别

### 错误反馈或错误修复

- 无论是bug反馈还是修复，都需要先创建一个问题，对bug进行详细描述，这样社区就可以通过问题记录轻松找到并查看问题和代码。bug反馈问题通常需要包含完整的bug信息描述和可重现的场景。

### 功能的实现，重构

- 如果你计划实现一个新功能（或重构），一定要通过 Issue 或其他方式与 eventmesh 核心开发团队沟通，并在沟通过程中详细描述新功能（或重构）、机制和场景。

### 文档改进

- 你可以在 [eventmesh-docs](https://github.com/apache/incubator-eventmesh/tree/master/docs) 找到 eventmesh 文档，该文档的补充或改进方式对 eventmesh 也是必不可少的。

## 贡献方式

There are two ways for new contributors to contribute to the eventmesh community:

- 如果你在 eventmesh 代码中发现了一个你想修复的 bug，或者你为 eventmesh 提供了一个新功能，请在 eventmesh 中提交一个问题，并向 eventmesh 提交一份 PR。

- eventmesh 社区中的其他贡献者提出的问题，这里社区整理的 [`issue for first-time contributors`](https://github.com/apache/incubator-eventmesh/issues/888) 是相对简单的 PR，可以帮助你熟悉向 eventmesh 社区做贡献的过程。

## 提交Issue指南

- 如果你不知道如何在 eventmesh 上提出问题，请阅读 [about the issue](https://docs.github.com/cn/issues/tracking-your-work-with-issues/quickstart) 。

- 在 eventmesh 社区，有问题模板可以参考，如果类型匹配请使用该模板，如果问题模板不符合你的要求，你可以开一个空的问题模板，对于问题请带上其匹配的功能标签。

- 对于问题的名称，请用一句话简要描述你的问题或目的，为了更好的全球交流，请用英文书写。

##  Pull请求（pr）提交指南

- 如果你不知道如何为 eventmesh 发起一个 PR，请详见 [about pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) 。

- 无论是 bug 修复，还是新功能开发（如果这个 pr 是新功能开发，那么关于新功能的文档更新应该包括在这个 pr 中），请向当前开发分支 master 提交 PR。

- 提交的pr应该遵循eventmesh提供的模板以及需要写的提交信息，简单描述你提交的pr是做什么的就可以了，请阅读 [模板详情](https://github.com/apache/incubator-eventmesh/blob/master/.github/PULL_REQUEST_TEMPLATE.md) 。

- 你提交的PR需要与你要修复的问题，或你要提出的问题相关联，所以你的PR标题应该以[ISSUE #xx]开头。

- 如果你的修改是关于一个错别字或小的优化，你不需要创建一个问题，只要提交一个PR和标题为[MINOR]。

**注意：**

- 一个拉动请求不应该太大。如果需要大量的修改，最好将这些修改分成几个单独的 PR。

- 在创建PR后，一个或多个提交人将帮助审查该拉动请求，在批准后，该PR将被合并到eventmesh主源库中，相关的Issue将被关闭。

## 审查

### PR审查

所有的代码都应该由一个或多个提交者进行良好的审查。一些原则。

- 可读性。重要的代码应该有良好的文档。遵守我们的 [代码风格](https://github.com/apache/incubator-eventmesh/blob/master/style/checkStyle.xml) 。

- 优雅性。新的函数、类或组件应该是精心设计的。

- 可测试性。重要的代码应该经过良好的测试（高单元测试覆盖率）。

### 许可证审查

EventMesh遵循 [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html) 政策。所有源文件应
在文件头中添加Apache许可证头。EventMesh 使用 [apache/skywalking-eyes](https://github.com/apache/skywalking-eyes) 来检查
源文件的头。

### PR合并

当一个PR被至少一个提交者批准后，它就可以被合并了。合并前，提交者可以对提交信息进行修改，要求提交的
消息要清楚，不能有重复，并使用 Squash 和 Merge 来确保一个 PR 只应包含一个提交。
对于大型的多人PR，使用Merge合并，在合并前通过rebase修复提交。

## 社区

### 联系我们

Mail: dev@eventmesh.apache.org