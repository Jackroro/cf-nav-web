
## 声明与介绍
- **代码修复**：源代码来源于https://github.com/lineagett/cf-workers-nav,  经AI迭代十二次，终于显示没有任何问题了。
- **教程更新**：原项目的教程有点难操作，经个人实践，现教程对新手小白更加友好。

---
# 部署到Cloudflare

## 1. 部署步骤

1. 登录 Cloudflare
2. 创建 Workers，选择 Hello World 选项
3. 复制仓库里 `workers.js` 的代码
4. 点击部署

## 2. 创建KV存储

新建一个名为 **CARD_ORDER** 的KV存储，用于存储数据。

## 3. 添加环境变量

在 Workers 设置里添加以下环境变量：

- **ADMIN_PASSWORD**：管理员登录密码
- **JWT_SECRET**：用于加密 Token，输入任意随机字符串即可

## 4. 绑定KV命名空间
在 Workers 设置里绑定KV命名空间

| 配置项 | 值 |
|--------|-----|
| 变量名称 | CARD_ORDER |
| KV命名空间 | CARD_ORDER（之前创建的） |

## 5. 绑定新域名以便直接访问
部署完成的网站是无法直接打开的。可在dnshe网站上免费注册一个域名，然后在网站内更改成CF给的DNS，其他内容不动，接着在CF上绑定刚注册的域名，这样你就收获了一个可以直接在国内直接访问的网站导航了。

## 6. 解决电脑无法直接访问的问题
直接连接后，过一些时间就无法直接访问了。可在CF里按以下步骤操作。
### 第一处：关闭 HTTP/3 和 0-RTT

1. 在左侧菜单栏，点击 **“速度”**（Speed）。
2. 点击展开下的 **“设置”**（Settings）。
3. 在页面中找到 **“协议优化”**（Protocol Optimization）这一栏：
   - **HTTP/3 (使用 QUIC)**：将右侧开关切换为 **“关闭”（Off）**。
   - **0-RTT 连接恢复**（0-RTT Connection Resumption）：同样切换为 **“关闭”（Off）**。

### 第二处：开启“始终使用 HTTPS”

1. 在左侧菜单栏，点击 **“SSL/TLS”**。
2. 点击展开下的 **“边缘证书”**（Edge Certificates）。
3. 往下拉页面，找到：
   - **始终使用 HTTPS**（Always Use HTTPS）：确保右侧开关是 **“开启”（On）**。
