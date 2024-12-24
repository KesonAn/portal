---
title: goctl 安装
sidebar_label: goctl 安装
slug: /docs/tasks/installation/goctl
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import DocsCard from '@components/global/DocsCard';
import DocsCards from '@components/global/DocsCards';

## 概述

goctl 是 go-zero 的内置脚手架，是提升开发效率的一大利器，可以一键生成代码、文档、部署 k8s yaml、dockerfile 等。

## Golang 直装

:::note 注意
此安装方法使用于已经安装了 `Golang`，对操作系统不做要求。
:::

### 1.1. 查看 go 版本

```bash
$ go version
```

### 1.2. go [get, install]

- 如果 go 版本在 `1.16` 以前，则使用如下命令安装：

  ```bash
  $ GO111MODULE=on go get -u github.com/zeromicro/go-zero/tools/goctl@latest
  ```

- 如果 go 版本在 `1.16` 及以后，则使用如下命令安装：

  ```bash
  $ go install github.com/zeromicro/go-zero/tools/goctl@latest
  ```

### 1.3. 验证

打开终端输入如下命令来验证是否安装成功：

```bash
$ goctl --version
```

## 手动安装

### 2.1 下载

<DocsCards>

<DocsCard
header="Microsoft Windows"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-windows-amd64.zip" >

<p>Windows Intel x86-64 位处理器</p>
<a>goctl-v1.7.3-windows-amd64.zip（21.7MB）</a>
</DocsCard>

<DocsCard
header="Microsoft Windows"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-windows-386.zip" >

<p>Windows Intel x86-32 位处理器</p>
<a>goctl-v1.7.3-windows-386.zip（20.6MB）</a>
</DocsCard>

<DocsCard
header="Apple macOS（ARM64）"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-darwin-arm64.tar.gz" >

<p>支持 macOS Apple 64 位处理器</p>
<a>goctl-v1.7.3-darwin-arm64.tar.gz（21.3MB）</a>
</DocsCard>

<DocsCard
header="Apple macOS（x86-64）"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-darwin-amd64.tar.gz" >

<p>支持 macOS 64 位处理器</p>
<a>goctl-v1.7.3-darwin-amd64.tar.gz（21.7MB）</a>
</DocsCard>

<DocsCard
header="Linux"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-linux-amd64.tar.gz" >

<p>支持 Linux 64 位处理器</p>
<a>goctl-v1.7.3-linux-amd64.tar.gz（21.7MB）</a>
</DocsCard>

<DocsCard
header="Linux"
href="https://github.com/zeromicro/go-zero/releases/download/tools%2Fgoctl%2Fv1.7.3/goctl-v1.7.3-linux-386.tar.gz" >

<p>支持 Linux 32 位处理器</p>
<a>goctl-v1.7.3-linux-386.tar.gz（20.3MB）</a>
</DocsCard>

</DocsCards>

###
:::note 注意
以上手动安装链接更新可能延迟，如需安装最新版本或者其他版本（其他操作系统及架构），请 [前往 Github](https://github.com/zeromicro/go-zero/releases) 查看。
:::

### 2.2 安装

解压下载的压缩包，并将其移动到 `$GOBIN` 目录，查看 `$GOBIN` 目录：

```bash
$ go env GOPATH
```

`GOBIN` 为 `$GOPATH/bin`，如果你的 `$GOPATH` 不在 `$PATH` 中，你需要将其添加到 `$PATH` 中。

### 2.3. 验证

安装完毕后，你可以执行如下指令来验证是否安装成功：

```bash
$ goctl --version
```

## Docker 安装

### 3.1 pull & run

<Tabs>

<TabItem value="amd64" label="amd64架构" default>

```bash
$ docker pull kevinwan/goctl
$ docker run --rm -it -v `pwd`:/app kevinwan/goctl --help
```

</TabItem>

<TabItem value="arm64" label="arm64(M1)架构" default>

```bash
$ docker pull kevinwan/goctl:latest-arm64
$ docker run --rm -it -v `pwd`:/app kevinwan/goctl:latest-arm64 --help
```

</TabItem>

</Tabs>

### 3.2 验证

打开终端输入如下指令来验证是否安装成功：

<Tabs>

<TabItem value="amd64" label="amd64架构" default>

```bash
$ docker run --rm -it -v `pwd`:/app kevinwan/goctl:latest --version
```

</TabItem>

<TabItem value="arm64" label="arm64(M1)架构" default>

```bash
$ docker run --rm -it -v `pwd`:/app kevinwan/goctl:latest-arm64 --version
```

</TabItem>

</Tabs>
