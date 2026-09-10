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

| 配置项 | 值 |
|--------|-----|
| 变量名称 | CARD_ORDER |
| KV命名空间 | CARD_ORDER（之前创建的） |

