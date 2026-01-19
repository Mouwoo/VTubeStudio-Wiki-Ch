

[**Web 挂件**](Web-Items.md) 只是在浏览器中运行的网站，因此它们本身可以是 VTS 插件并直接与 VTube Studio 交互。若要与 VTS API（或至少与挂件相关的结点）进行交互，Web 挂件需要知道自己的挂件实例 UUID，用于在 VTS 中标识它。

有关Web 挂件的更多常规信息，请查看[此页](Web-Items.md).

若要获取该 ID，可以使用以下 javascript 代码。需要用以下方法向 VTube Studio 发送 `vts_web_item_request_item_id` 消息:

```javascript
window.vuplex.postMessage('vts_web_item_request_item_id');
```

然后，VTube Studio 将向您传递挂件 UUID。您可以使用该 ID 来执行诸如移动挂件、固定/取消固定、删除它（从而关闭 API 连接，因为浏览器进程已关闭）等操作。

![web挂件api1](img/img/web_item_api_1.png){: height="" width="587px"}

```javascript
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>VTS Web Item ID Listener Example</title>
   </head>

   <body>

      <h1>VTS Web Item ID Listener Example</h1>
      <p id="messageDisplay">Waiting for message...</p>
      <p id="itemID">Waiting for item ID...</p>

      <script>
         if (window.vuplex)
         {
             addMessageListener();
         }
         else
         {
             window.addEventListener('vuplexready', addMessageListener);
         }
         
         function addMessageListener()
         {
             window.vuplex.addEventListener('message', function(event)
             {
                 let json = event.data;
                 let jsonParsed = JSON.parse(json);
         
                 // {"apiName": "VTubeStudioWebItemAPI", "messageType": "ItemID", "value": "129b5746777b4d5390ba8b36f4b4a515"}
                 document.getElementById('messageDisplay').textContent = 'Received JSON: ' + json;
                 document.getElementById('itemID').textContent = 'Item ID: ' + jsonParsed.value;
             });

             window.vuplex.postMessage('vts_web_item_request_item_id');
         }
      </script>
   </body>
</html>

```