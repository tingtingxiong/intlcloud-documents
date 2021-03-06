## 1. 接口描述
 此接口用于智能回复用户提问。
 调用协议：HTTP/HTTPS  GET 请求。

 ## 2. 请求参数
 |参数名称|参数类型|是否必填|参数说明|
 |------ |------|------ |----- |
 |appId	 |String |是 |应用 ID，可在 IASK 应用管理界面获取|
 |uuId   |String|是	|用户唯一 ID，最大长度 20 位|
 |channel|	Int	|是 |接口调用渠道，0：问答 API ，1：公众号，2：桌面网站，3：移动网站| 
 |query	|String|是	|用户查询问题|
 |time	|Int   |是	|时间戳，单位：秒|
 |sign	|String|是|调用签名，根据接口调用参数及应用 SecretKey 生成|


 ## 3. 响应参数
 |参数名|类型|说明|
 |:-----  |:-----|-----|
 |code|  Int |code 码，0 为正常，非 0 为异常  |
 |data|Object|返回结果|
 |msg |String|返回消息| 

 ## 4. 接入流程
 4.1 用户从 IASK 的应用获取 APPID 及 SecretKey； 
 4.2 确认除 sign 参数外各参数的值；
 4.3 生成 sign 参数，将 appId、uuId、channel、query、time 参数按升序排列组合成字符串得到`&appId=x&channel=x&query=x&time=x&uuId=x`；在字符串头部加上 SecretKey 得到`x&appId=x&channel=x&query=x&time=x&uuId=x`。对此字符串做 MD5 处理得到签名参数 sign。

 sign 参数生成示例（PHP）：
 ```
 $secret_key = xxx;  //  IASK 应用配置里面的 SecretKey
     'appId' => 'xx'
     'time' => 1525339871,
     'channel' => 'xx',
     'uuId' => 'xx',
     'query' => 'xx',
 ];
 ksort($params);
 foreach ($params as $key => $value) {
     $secret_key.= '&' . $key . '=' . $value;
 }
 $sign = md5($secret_key);
 ```
 ## 5. 示例
 ### 请求示例
 ```
 iask.qq.com/aics/open/ask?
 appId=817c0cc4fb65b98022b73b56485a515d&uuId=aa
 &channel=1
 &query=再来试试
 &time=1528012017
 &sign=dc0900e8209f1b3c16f4c0bb736d7a39
 ```
 ### 响应示例
 直接返回结果：
 ```
 {
     code: 0,
     data: {
         type => 'STRING',
         prefix => '',
         answer => 'xxxx', 
 		rel => [
             "xxx", 
             "xxx"
         ],
         suffix => '',
     },
     msg: "success"
 }
 ```

 追问返回结果：
 ```
 {
         code: 0,
         data: {
             type => 'ARRAY',
             prefix => '',
             answer => [
                 "xxx" ,
                 "xxx" ,
             ], 
             rel => [],
             suffix => '',
         },
         msg: "success"
     }
 ```