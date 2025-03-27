# 在 DatabaseMart VPS 上轻松安装 Coolify（Ubuntu 24.04 LTS 版）

Coolify 是一个现代化的开源自托管平台，可作为 Heroku 等服务的替代方案。本指南将详细介绍如何在运行 Ubuntu 24.04 LTS 的 DatabaseMart VPS 上安装 Coolify。

## 系统要求

在开始安装前，请确保您的 VPS 满足以下最低配置要求：

- **操作系统**：Ubuntu 24.04 LTS
- **CPU**：2 核
- **内存**：2 GB（建议 4 GB 以获得更好性能）
- **网络**：开放 22 端口用于 SSH 访问

## 准备工作

1. 已注册的域名
2. 基础的 Linux 命令行知识

👉 [【点击查看】2025年最新 DatabaseMart 优惠码及特价云服务器方案汇总](https://bit.ly/DatabaseMart)

## 安装步骤详解

### 第一步：获取 VPS 服务器

1. 在 DatabaseMart 购买 Linux VPS 服务器
2. 选择 Ubuntu 24.04 LTS 作为操作系统

### 第二步：初始服务器设置

通过 SSH 连接到您的 VPS：

bash
ssh root@your_server_ip

更新系统软件包：

bash
sudo apt update && sudo apt upgrade -y

### 第三步：安装 Coolify

使用快速安装方法运行安装脚本：

bash
curl -fsSL https://cdn.coollabs.io/coolify/install.sh | bash

安装过程可能需要几分钟时间，请耐心等待。

### 第四步：访问 Coolify

安装完成后，通过以下地址访问 Coolify：

http://yourIP:8000

按照提示创建管理员账户。

## 高级配置

### 设置完全限定域名

不建议直接通过 IP 地址访问 Coolify，建议配置 SSL 安全访问：

1. 在域名注册商处添加 A 记录，指向您的服务器 IP
2. 等待 DNS 解析生效
3. 在 Coolify 仪表板的"设置"中配置您的域名（务必包含 https://）

### 安全建议

- 启用双因素认证(2FA)
- 定期更新系统和 Coolify 版本
- 配置防火墙规则限制访问

## 后续操作

成功安装 Coolify 后，您可以通过仪表板：

- 部署各类应用程序
- 管理数据库服务
- 监控资源使用情况

## 常见问题

**Q：安装过程中出现错误怎么办？**
A：检查系统日志 `/var/log/syslog` 获取详细错误信息，确保满足系统要求。

**Q：如何升级 Coolify？**
A：Coolify 会自动检查更新，您也可以在设置中手动触发更新。

**Q：支持哪些部署方式？**
A：支持 Git、Docker 等多种部署方式，满足不同开发需求。