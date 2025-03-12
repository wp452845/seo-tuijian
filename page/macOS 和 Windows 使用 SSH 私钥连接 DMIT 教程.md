# macOS 和 Windows 使用 SSH 私钥连接 DMIT 教程

在之前的文章中，我们已经介绍了如何注册和购买 DMIT VPS。由于 DMIT 出于安全性考虑，不支持使用 root 密码进行远程连接，只能通过 SSH 私钥登录。对于新手来说，可能不知道如何使用 SSH 私钥在本地连接 VPS。本文将分别演示在 macOS 和 Windows 系统中如何通过 SSH 私钥远程登录 DMIT VPS。

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

## 一、如何下载 DMIT SSH 密钥

要连接 DMIT VPS 的第一步是获取 SSH 密钥。进入 DMIT 后台管理界面，转到相应的服务页面，点击“SSH 金鑰管理”，即可下载每台 VPS 对应的 SSH 密钥文件。

需要注意的是，**SSH 密钥只能下载一次**，如果丢失，需要重新生成。在后台进入管理页面点击重新生成按钮，生成新的密钥后，务必重启 VPS（点击 “Reboot” 按钮），以确保新密钥生效。

默认情况下，系统会同时下载公钥（public_key）和私钥（private_key）。我们只需要 **private_key** 文件即可。

在下载的 private_key 文件夹中，通常包含两个文件：

- 一个是 `.ppk` 格式
- 一个是 `.pem` 格式

## 二、macOS 使用 SSH 私钥连接 DMIT

macOS 系统可以使用自带的终端工具通过 SSH 私钥连接 DMIT。具体步骤如下：

### 1. 修改私钥权限

在使用私钥之前，需要确保文件权限足够安全，否则系统可能会拒绝连接。在终端中执行以下命令：

bash
chmod 600 id_rsa.pem


### 2. 通过 SSH 私钥连接 VPS

使用以下命令进行连接：

bash
ssh -i id_rsa.pem root@DMIT_VPS_IP


将 `id_rsa.pem` 替换为你的私钥文件名，将 `DMIT_VPS_IP` 替换为你的 VPS IP 地址。

## 三、Windows 使用 SSH 私钥连接 DMIT

对于 Windows 用户，可以通过工具如 PuTTY 或 XShell 来连接 DMIT VPS。本文以 **PuTTY** 为例，演示连接过程。

### 1. 配置 PuTTY 连线信息

打开 PuTTY，输入你的 DMIT VPS 的 IP 地址，并选择 “SSH” 为连接类型。

接着，点击左侧菜单栏中的 **Connection** > **Data**，在 “Auto-login username” 输入框中填写 `root`。

### 2. 添加私钥文件路径

展开左侧菜单栏中的 **SSH**，点击 **Auth**，然后点击 “Browse” 按钮，选择下载的 `.ppk` 格式私钥文件。

### 3. 连接 VPS

配置完成后，点击 “Open” 按钮，就可以成功登录到 DMIT VPS。

## 总结

以上内容即为 macOS 和 Windows 中使用 SSH 私钥连接 DMIT VPS 的完整教程。由于基于私钥的连接方式更加安全，可能对一些新用户来说稍显复杂，但只要按照步骤操作即可轻松完成。希望本教程能为大家带来帮助。