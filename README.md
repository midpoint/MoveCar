# MoveCar

自定义挪车码，可以放到 cloudflare workers pages 中使用

## 使用前
请设置好几个变量：
### 设置车主相关信息、通知密钥
  - const phone = '139xxxxxxxx'; // 车主的手机号
  - const wxpusherAppToken = 'AT_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx'; // Wxpusher APP Token
  - const wxpusherUIDs = ['UID_sxxxxxxxxxxxxxxxxxxxxxxxxxxxxx']; // 车主的UIDs
  
### 使用验证码功能
要使用这个功能，您需要：
在 Cloudflare 的仪表板中创建一个 Turnstile 站点
替换代码中的两个关键值：
- YOUR_SITE_KEY：替换为您的 Turnstile Site Key（在前端代码中）
- YOUR_SECRET_KEY：替换为您的 Turnstile Secret Key（在后端验证函数中）

## 示例图
![示例](https://i.imgur.com/K0Ba5Z9.jpeg)
