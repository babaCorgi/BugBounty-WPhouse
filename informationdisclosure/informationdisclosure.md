# InformationDisclosure
信息泄露(InformationDisclosure)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**我如何接管 Wordpress 管理员 fiiipay.my**](https://sahruldotid.medium.com/how-i-takeover-wordpress-admin-fiiipay-my-1bdede83635d)  
存在默认文件/setup-config.php可配置wordpress  

2. [**Facebook BugBounty——披露页面成员**](https://medium.com/@tnirmalz/facebook-bugbounty-disclosing-page-members-1178595cc520)  
由于某些隐私原因，页面成员（管理员/模组/分析师）的身份被 facebook 保密  
facebook发送帖子存在一个发送消息聊天的功能（使用该功能的端点返回了创建帖子的创建者的ID）  
后续发现如果创建者回复消息也可从响应包中发现ID  

3. [**通过端口 8009 访问 VoIP 内部服务：通过本地 Apache 代理路由流量**](https://batee5a.medium.com/accessing-voip-internal-service-via-port-8009-routing-traffic-through-local-apache-proxy-54a4ff539c5f)  
本地部署apache代理JServ 协议流量访问VoIP面板  
VoIP面板禁用js实现后台未授权访问。  

4. [**PWNING EBAY - 我如何抛弃 EBAY 日本的网站源代码**](https://slashcrypto.org/2018/11/28/eBay-source-code-leak/)  
通过GitTools发现www.ebay.co.jp/.git/HEAD的git泄露  
泄露了大量源代码和数据库密码等等  

5. [**披露任何 Facebook 应用程序的contact_email**](https://www.amolbaikar.com/disclose-contact_email-of-any-facebook-application/)  
使用 Graph API 访问此字段是安全的，但将查询字段更改为 GraphQL 调用，我能够访问任何 Facebook 应用程序的电子邮件 ID  

6. [**广告 API 中的 Facebook 源代码披露**](https://www.amolbaikar.com/facebook-source-code-disclosure-in-ads-api/)  
端点的弱点是上传损坏的图像或无效的 BASE64 字符串，然后应用程序无法正确处理处理图像调整大小期间发生的异常错误。  
PHP 脚本错误揭示了程序的一些内部路径、功能。端点处理错误/异常很差，通常用户无法访问内部堆栈跟踪。  

7. [**从 CTF 到 Bug Bounty 战利品**](https://medium.com/@benjitobias/from-ctfs-to-bug-bounty-booty-81bab999b70d)  
访问子域office.tailorstore.com获得了一个401  
访问/.git/获得403，访问任意url/.giss/也是401，回显不同  
尝试/.git/HEAD成功访问，确认存在信息泄露  