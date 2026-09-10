一、部署到Cloudflare
1、部署步骤
登录 Cloudflare:创建workers，选择hello world 选项，然后复制仓库里workers.js的代码，然后点击部署
2、创建KV存储
新建一个名为CARD_ORDER的KV存储，用于存储数据
3、添加环境变量
是在workers步骤这里，添加变量，在设置里。
ADMIN_PASSWORD，管理员登录密码
JWT_SECRET，用于加密 Token，输入点随机字符串即可。
4、绑定KV命名空间
变量名称为CARD_ORDER，KV选择之前创建好的CARD_ORDER
