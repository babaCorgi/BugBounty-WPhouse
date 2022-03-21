# IDOR
不安全的对象引用(IDOR)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**我如何能够删除 Google 图库数据 [IDOR]**](https://medium.com/@yogeshtantak7788/how-i-was-able-to-delete-google-gallery-data-idor-53d2f303efff)  
DELETE /xxx/xxx/xxx/xxx_id  
越权删除用户的图片收藏  

2. [**我如何能够接管所有用户帐户和管理面板**](https://addictivehackers.blogspot.com/2018/12/how-i-was-able-to-takeover-all-user.html)  
某个子域abc.example.com/robots.txt  
发现敏感目录/user重定向到https://abc.example.com/user/16397/edit可更改用户密码  
尝试https://abc.example.com/user/1/edit可修改管理员密码  

3. [**我如何能够为任何 Facebook 用户生成访问令牌。**](https://infosecwriteups.com/how-i-was-able-to-generate-access-tokens-for-any-facebook-user-6b84392d0342)  
易受攻击的端点在向其发出 POST 请求时返回一个页面 access_token 以及参数page_id。  
这使我可以发出请求并将 page_id 值更改为任何 Facebook 用户 ID，并且作为对该请求的响应，我获得了该用户的访问令牌  

4. [**更改任何人的头像-利用 IDOR**](https://medium.com/@rupika.luhach/change-anyones-profile-picture-exploiting-idor-41369f5acf75)  
上传头像包存在一个id值，越权导致。  

5. [**我是如何绕过电子邮件验证的**](https://blog.securitybreached.org/2018/12/08/how-i-was-able-to-bypass-email-verification/)  
POST /registerNewUser存在一个参数email=test@gmail.com越权泄露了验证链接  
返回包存在{“key”:”验证链接”,”success”:1}  

6. [**IRCTC — 数百万乘客信息面临巨大风险！**](https://logicbomb.medium.com/irctc-millions-of-passenger-details-left-at-huge-risk-18c5ecc09d7f)  
https://www.shriramgi.com/irctc-nominee.html?TXNId=10000139XX根据交易号 (TXNId)，正在检索所有乘客信息  
发现某个端点存在修改请求以提供 PNR 号作为输入并接收交易号作为响应  
然而PNR号为10位且前3位固定，且该端点无速率限制  
于是可遍历PNR到遍历交易号获取用户信息。  