---
title: 这才是真正的Git——Git内部原理揭秘！
subtitle:
index_img: /img/git2.jpeg
banner_img: /img/ElPit.jpg
date: 2020-09-03 10:00:00
---

## 看，有几个 git 的常用命令！

<!-- ### 创建一个版本库

```bash
$ git init
```

{% note success %}
INFO

可以看到目录下多了一个.git 隐藏目录，这就是版本库目录
{% endnote %} -->

### 版本创建

```bash
$ git add filename
$ git commit -m '版本描述'
```

### 查阅版本记录

```bash
#输出版本库日志
$ git log
#将每条日志的输出为一行
$ git log -oneline
#查看操作记录
$ git reflog
```

### 版本回退&撤销

```bash
# 丢弃工作区的文件
$ git checkout - filename
# 回滚暂存区的文件
$ git reset HEAD -filename
# 回到最新一次提交
$ git reset - hard HEAD^ -filename
# 撤销指定版本（撤销也会作为一次提交被保存）
$ git revert <commit_id>

```

{% note warning %}
**git revert 和 git reset 的区别**

- git revert 是用一次新的 **_commit_** 来回滚之前的 **_commit_**，此次提交之前的 **_commit_** 都会被保留;
- git reset 是回到某次提交，提交及之前的 **_commit_** 都会被保留，但是此 {% label default @commit_id %} 之后的修改都会被删除;
  {% endnote %}
