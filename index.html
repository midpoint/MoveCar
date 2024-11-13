addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request))
})


async function handleRequest(request) {

  // 车主的手机号和 Wxpusher 的信息, 这些信息可以用workers变量配置
  const phone = '139xxxxxxxx'; // 车主的手机号
  const wxpusherAppToken = 'AT_xxxxxxxxxxxxxxxxxxxxxxxxxxxxx'; // Wxpusher APP Token
  const wxpusherUIDs = ['UID_sxxxxxxxxxxxxxxxxxxxxxxxxxxxxx']; // 车主的UIDs


  if (request.method === 'POST') {
    // 处理 POST 请求，用于发送通知
    const data = await request.json();

    if (data.action === 'notifyOwner') {
      // 调用 Wxpusher API 发送通知
      const response = await fetch("https://wxpusher.zjiecode.com/api/send/message", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          appToken: wxpusherAppToken,
          content: "您好，有人需要您挪车，请及时处理。",
          contentType: 1,
          uids: wxpusherUIDs,
        }),
      });

      const result = await response.json();
      if (result.code === 1000) {
        return new Response(JSON.stringify({ message: '通知已发送！' }), {
          headers: { "Content-Type": "application/json" },
        });
      } else {
        return new Response(JSON.stringify({ message: '通知发送失败，请稍后重试。' }), {
          headers: { "Content-Type": "application/json" },
        });
      }
    }
  }

  // 获取手机号的请求
  if (request.url.includes('/getPhoneNumber')) {
    return new Response(JSON.stringify({ phone: phone }), {
      headers: { "Content-Type": "application/json" },
    });
  }

  // 返回 HTML 页面
  const htmlContent = `
    <!DOCTYPE html>
    <html lang="zh-CN">
      <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>通知车主挪车</title>
        <script src="https://unpkg.com/qrcodejs@1.0.0/qrcode.min.js"></script>
        <style>
          * { box-sizing: border-box; margin: 0; padding: 0; }
          body { font-family: Arial, sans-serif; display: flex; align-items: center; justify-content: center; height: 100vh; background: #f0f2f5; color: #333; }
          .container { text-align: center; padding: 20px; width: 100%; max-width: 400px; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); background: #fff; }
          h1 { font-size: 24px; margin-bottom: 20px; color: #007bff; }
          p { margin-bottom: 20px; font-size: 16px; color: #555; }
          button { 
            width: 100%; 
            padding: 15px; 
            margin: 10px 0; 
            font-size: 18px; 
            font-weight: bold; 
            color: #fff; 
            border: none; 
            border-radius: 6px; 
            cursor: pointer; 
            transition: background 0.3s; 
          }
          .notify-btn { background: #28a745; }
          .notify-btn:hover { background: #218838; }
          .call-btn { background: #17a2b8; }
          .call-btn:hover { background: #138496; }
          /* 添加二维码相关样式 */
          .qrcode-container {
              margin-top: 20px;
              padding-top: 20px;
              border-top: 1px solid #eee;
          }
  
          .qrcode-container p {
              font-size: 14px;
              color: #666;
              margin-bottom: 10px;
              text-indent: 0.2em !important;
          }
  
          #qrcode {
              display: flex;
              justify-content: center;
              margin: 0 auto;
          }
        </style>
      </head>
      <body>
        <div class="container">
          <div id="mainPanel">  
            <h1>通知车主挪车</h1>
            <p>如需通知车主，请点击以下按钮</p>
            <button class="notify-btn" onclick="notifyOwner()">通知车主挪车</button>
            <button class="call-btn" onclick="getPhoneNumber()">拨打车主电话</button>
          </div>
          <div class="qrcode-container">
            <p>打印挪车二维码</p>
            <div id="qrcode"></div>
          </div>
        </div>
        <script>
        window.addEventListener('load', function () {
        // 生成二维码
            try {
                const currentUrl = window.location.href;
                console.log('Current URL:', currentUrl); // 调试用

                new QRCode(document.getElementById("qrcode"), {
                    text: currentUrl,
                    width: 128,
                    height: 128,
                    colorDark: "#000000",
                    colorLight: "#ffffff",
                    correctLevel: QRCode.CorrectLevel.H
                });
            } catch (error) {
                console.error('QR Code generation error:', error); // 调试用
            }
        });  
        // 发送通知请求到 Worker
          function notifyOwner() {
            fetch("/notify", {
              method: "POST",
              headers: { "Content-Type": "application/json" },
              body: JSON.stringify({ action: "notifyOwner" })
            })
            .then(response => response.json())
            .then(data => {
              alert(data.message);
            })
            .catch(error => {
              console.error("Error sending notification:", error);
              alert("通知发送出错，请检查网络连接。");
            });
          }

          // 获取车主手机号并拨打电话
          function getPhoneNumber() {
            fetch("/getPhoneNumber")
            .then(response => response.json())
            .then(data => {
              window.location.href = "tel:" + data.phone;
            })
            .catch(error => {
              console.error("Error getting phone number:", error);
              alert("获取手机号出错，请检查网络连接。");
            });
          }
        </script>
      </body>
    </html>
  `;

  return new Response(htmlContent, {
    headers: { 'Content-Type': 'text/html;charset=UTF-8' },
  });
}
