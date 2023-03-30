# 发布带有实时内核补丁的 Red Hat Enterprise Linux 8.1

> 原文：<https://thenewstack.io/red-hat-enterprise-linux-8-1-released-with-live-kernel-patching/>

2019 年 11 月 5 日星期二，红帽企业版 Linux 最新版本正式发布。RHEL 8.1 是 Red Hat 旗舰操作系统第八次迭代的第一个次要版本，并带来了一些重要的更新，这些更新围绕着跨混合云的传统和云原生基础架构部署的可管理性和安全性。

Red Hat 总裁兼总经理斯蒂芬妮·奇拉维斯表示:“混合云由一致、可靠和更安全的基础推动，我们将 Red Hat Enterprise Linux 设计为企业计算未来的基石。

红帽 8.1 是 RHEL 的第一个版本，遵循了 2019 年红帽峰会上宣布的可预测的发布节奏。这个新的节奏承诺每六个月发布一次小版本。这样的时间表给了 Red Hat 客户和客户更好地准备新版本的能力。知道每六个月就会有一个小版本发布，公司就可以安排部署，将计划外中断和停机时间降到最低。

但是在红帽的最新版本中能找到的最好的特性是什么呢？让我们来看看。

## 实时补丁在这里

如果有一个最令人兴奋的特性，那就是实时内核补丁。什么是实时内核补丁？这个新添加的功能允许管理员在内核中修补安全漏洞(和其他更新),而不必重新启动系统。对于企业而言，这意味着正常运行时间的显著改善。

## 以容器为中心的 SELinux 概要文件

在 RHEL 8.1 之前，容器管理员的任务可能是处理 SELinux——这并不容易。新版本提供了特定的 SELinux 配置文件，用于更细粒度地控制容器化的工作负载和主机系统如何交互。这些新的配置文件将大大有助于限制云原生应用程序带来的威胁。围绕容器的安全问题一直存在，以容器为中心的新 SELinux 配置文件将使强化生产系统以抵御针对云原生应用的安全威胁成为可能，并使创建定制的安全策略以控制容器化服务如何访问主机系统资源变得更加容易。

说到安全性…

## 系统角色

Red Hat Enterprise Linux 8.1 增加了新的系统角色，以简化配置 RHEL 来处理特定功能的过程，这有助于扩展现有的 Ansible DevOps 系统角色。这些新角色将简化 Linux 子系统(如存储、网络、时间同步、kdump、SELinux 等)的管理，并更有效地处理物理、虚拟和基于云的环境中大型部署的细微差别。

## 通常的更新

当然，the 8.1 更新还包括系统应用、服务和开发者工具的常规更新。你会看到像 PHP 7.3、Ruby 2.6、Node.js 12、NGINX 1.16、LLVM 8.0.1、Rust Toolset 1.37、Go Toolset 1.12.8 等等更新。

## 获得 RHEL 8.1

对于红帽的用户来说，新发布的 RHEL 可以从红帽客户门户网站获得。登录并从 Red Hat 获得您的最新和最棒的副本。

Red Hat OpenShift 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>