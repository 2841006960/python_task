# 实验一 Git和Markdown基础

班级：22物联2  
学号：B20220305211  
姓名：李德喜  
Github地址：<https://github.com/2841006960/python_task>

---

## 实验目的

1. 学习Git基础，掌握使用Git进行版本控制的基本操作。
2. 学习Markdown语法，使用Markdown进行文档编辑和记录。
3. 掌握VSCode的基本使用，包括插件的配置和代码的编写。

## 实验环境

1. Git
2. VSCode
3. VSCode插件

## 实验过程记录

Git实验过程的记录请参考[Learning Git Branch Tutorial](https://github.com/zhoujing204/python_course/blob/main/Labs/LearningGitBranch-Tutorial.md)，以下是各个Git小实验的记录：

### 第1个小实验：Git Commit
- **动机**: 使用`git commit`将当前的修改保存到本地仓库的历史记录中，是版本控制的核心操作之一。
- **使用的git命令**:
  ```shell
  git commit
  ```
- **git命令的解释**: `git commit`命令用于将已暂存的文件更改提交到本地仓库中，每次提交都会生成一个唯一的提交ID，用于跟踪变更。

### 第2个小实验：Git Branch
- **动机**: 使用分支可以将不同的功能开发隔离开来，便于并行开发。
- **使用的git命令**:
  ```shell
  git branch bugFix
  git checkout bugFix
  ```
- **git命令的解释**: `git branch`命令用于创建一个新分支，而`git checkout`则切换到指定的分支。

### 第3个小实验：Git Merge
- **动机**: 将两个分支的改动合并，可以将开发功能整合到主分支中。
- **使用的git命令**:
  ```shell
  git branch bugFix
  git checkout bugFix
  git commit
  git checkout main
  git commit
  git merge bugFix
  ```
- **git命令的解释**: `git merge`用于合并指定分支到当前分支，以实现代码的集成。

### 第4个小实验：Git Rebase
- **动机**: 通过变基，重写提交历史，使提交记录更加整洁。
- **使用的git命令**:
  ```shell
  git branch bugFix
  git checkout bugFix
  git commit
  git checkout main
  git commit
  git checkout bugFix
  git rebase main
  ```
- **git命令的解释**: `git rebase`可以将一个分支的提交移动到另一个分支的顶端，重构提交历史。

### 第5个小实验：分离 HEAD
- **动机**: 分离HEAD可用于回溯到某个特定的提交记录进行查看或修改。
- **使用的git命令**:
  ```shell
  git checkout c4
  ```
- **git命令的解释**: `git checkout`可以让HEAD指向特定的提交，而不是分支名。

### 第6个小实验：相对引用（^）
- **动机**: 使用相对引用访问父提交记录，便于在提交历史中快速跳转。
- **使用的git命令**:
  ```shell
  git checkout bugFix^
  ```
- **git命令的解释**: 在`bugFix`的父提交位置进行切换。

### 第7个小实验：相对引用2（~）
- **动机**: 相对于特定提交向前移动多步，便于快速访问之前的提交。
- **使用的git命令**:
  ```shell
  git branch -f bugFix HEAD~2
  git branch -f main c6
  git checkout C1
  ```
- **git命令的解释**: `HEAD~2`代表距离HEAD的两个提交之前。

### 第8个小实验：撤销变更
- **动机**: 撤销错误提交或者回退到之前的代码状态，保持代码版本稳定。
- **使用的git命令**:
  ```shell
  git reset HEAD~
  git checkout pushed
  git revert HEAD
  ```
- **git命令的解释**: `git reset`重置到某个版本，`git revert`用于创建一次新的提交来撤销某次特定的提交。

### 第9个小实验：Git Cherry-pick
- **动机**: 将某些特定的提交应用到当前分支，灵活选择变更。
- **使用的git命令**:
  ```shell
  git cherry-pick c3 c4 c7
  ```
- **git命令的解释**: `git cherry-pick`用于将其他分支上的特定提交应用到当前分支。

### 第10个小实验：交互式 Rebase
- **动机**: 对提交记录进行整理和重写，提高历史记录的可读性。
- **使用的git命令**:
  ```shell
  git rebase -i c1 main
  ```
- **git命令的解释**: 交互式变基可以对多个提交进行编辑、删除、合并或重排序。

以下是补充的第11到18个实验的内容：

---

### 第11个小实验：Git Clone
- **动机**: 使用`git clone`可以从远程仓库复制一份代码到本地，便于在本地进行开发和测试。
- **使用的git命令**:
  ```shell
  git clone <repository-url>
  ```
- **git命令的解释**: `git clone`命令用于从远程仓库创建一个本地副本，包含所有的版本历史，方便开发者进行修改和版本管理。

### 第12个小实验：远程分支
- **动机**: 使用远程分支可以让团队成员共享和管理代码，保持代码库的一致性。
- **使用的git命令**:
  ```shell
  git commit
  git checkout o/main
  git commit
  ```
- **git命令的解释**: `git checkout o/main`用于切换到远程分支，`git commit`用于提交当前修改到本地。

### 第13个小实验：Git Fetch
- **动机**: `git fetch`用于从远程仓库获取最新的提交记录，以便更新本地分支的信息。
- **使用的git命令**:
  ```shell
  git fetch
  ```
- **git命令的解释**: `git fetch`命令用于下载远程分支的更新，但不自动合并到当前分支，方便开发者选择性地合并。

### 第14个小实验：Git Pull
- **动机**: `git pull`命令用于从远程仓库获取最新提交并合并到当前分支，保持本地代码与远程一致。
- **使用的git命令**:
  ```shell
  git pull
  ```
- **git命令的解释**: `git pull`命令实际上是`git fetch`和`git merge`的组合，可以直接将远程的变更合并到本地分支。

### 第15个小实验：模拟团队合作
- **动机**: 模拟团队合作可以帮助理解如何在团队环境中使用Git进行协作和版本管理。
- **使用的git命令**:
  ```shell
  git clone <repository-url>
  git fakeTeamwork 2
  git commit
  git pull
  ```
- **git命令的解释**: 在模拟团队合作中，通过`git fakeTeamwork`可以在远程主分支上提交变更，然后通过`git pull`更新本地分支。

### 第16个小实验：Git Push
- **动机**: 使用`git push`将本地提交推送到远程仓库，分享代码和更新。
- **使用的git命令**:
  ```shell
  git commit
  git commit
  git push
  ```
- **git命令的解释**: `git push`命令用于将本地分支的提交上传到远程仓库，更新远程代码库。

### 第17个小实验：偏离的提交历史
- **动机**: 理解如何处理偏离的提交历史，学习解决合并冲突的方法。
- **使用的git命令**:
  ```shell
  git clone <repository-url>
  git fakeTeamwork
  git commit
  git pull --rebase
  git push
  ```
- **git命令的解释**: 在处理偏离的提交历史时，使用`git pull --rebase`可以避免产生合并提交，从而保持提交历史的整洁。

### 第18个小实验：锁定的Main (Locked Main)
- **动机**: 理解如何在多分支环境中锁定主分支，确保主分支的稳定性。
- **使用的git命令**:
  ```shell
  git branch feature
  git branch -f main o/main
  git checkout feature
  git push
  ```
- **git命令的解释**: `git branch -f`用于强制将主分支指向某个特定的提交，`git push`将特性分支推送到远程，保持主分支的锁定状态。

## 实验总结

通过这次实验，我学会了使用Git进行版本控制的基本操作，包括分支管理、合并、变基等技术。掌握了Markdown语法，可以用于文档的快速编写和排版。此外，学会了VSCode的使用和配置，尤其是如何高效地进行代码编辑和管理。这些知识将为我的未来项目开发和团队协作提供重要支持。