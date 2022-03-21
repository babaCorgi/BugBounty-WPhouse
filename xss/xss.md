# XSS
跨站脚本(XSS)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**ws-na.amazon-adsystem.com(Amazon) 上的反射型 XSS**](https://medium.com/@newp_th/reflected-xss-on-ws-na-amazon-adsystem-com-amazon-f1e55f1d24cf)  
https://ws-na.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=US&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=jgsbookselection%22%3E%3Cscript/k/%3Ealert(113)% 3C/script/k/%3E&marketplace=amazon®ion=US&placement=1449319432&asins=1449319432&linkId=cc38d5883c3f92bbeb69b93a6810322a&show_border=true&link_opens_in_new_window=true  

2. [**Stack Overflow 上的反射型 XSS**](https://medium.com/@newp_th/reflected-xss-on-stack-overflow-b8366a855472)  
通过burp插件查找到一个cookie参数prov=xxxx-xxxx-xxxx"></script><img src=x onerror=alert(1)>  

3. [**XSS 蠕虫——对 Web 应用程序漏洞的创造性利用**](https://blog.compass-security.com/2018/12/xss-worm-a-creative-use-of-web-application-vulnerability/)  
邮件消息蠕虫，使用<svg onload=eval(atob(p))><svg onload=p+='base64xxxxxxx'>绕过  

4. [**自我 XSS 到有趣的存储 XSS**](https://nahoragg.github.io/bugbounty/2018/12/15/Self-XSS-to-Interesting-Stored-XSS.html)  
AngularJSXss使用模板注入{{4*4}}反映16表示存在  
使用{{constructor.constructor('alert(“XSS”)')()}}反映xss  
可惜为self-xss，在敏感角落发现退订链接回显了xss不为self  

5. [**由于不正确转义的 JSON 数据，XSSing Google Code-in**](https://websecblog.com/vulns/google-code-in-xss/)  
Google Code-in是由 Google 主办的面向学生的在线编程竞赛  
注册字段存在self-xss和评论字段也存在xss  
<script>像这样的元素将无法通过 CSP，  
使用{{constructor.constructor('alert("xss")')()}}执行AngularJS  

6. [**我的第一篇错误赏金文章**](https://medium.com/@sampanna/self-xss-in-indeed-com-e0c99c104cba)  
一个为工作设置警报的填写选项注入payload即可得  

7. [**如何在 ProtonMail iOS 应用程序中意外找到 XSS**](https://www.secu.ninja/2018/12/04/how-to-accidentally-find-a-xss-in-protonmail-ios-app/)  
测试某个应用reseracher 帐户中的帐户名称和个人详细信息更改为 XSS 字符串  
没有回显，但是某一天iPhone 上的ProtonMail收件箱收到的邮件发现了xss  
所以 iOS 上的ProtonMail应用程序没有过滤掉 <script> 标签。  

8. [**关于我的第一个漏洞赏金的故事**](https://medium.com/@sudhanshur705/story-about-my-first-bug-bounty-9fe710be8241)  
1.ucweb.com下xss
https://sudhanshur705.medium.com/story-about-my-first-bug-bounty-9fe710be8241
https://virustotal.com找到阿里巴巴子域samsung.ucweb.com访问403
通过site:samsung.ucweb.com找到http://samsung.ucweb.com/webstore/classify.html?dataKey=LifeStyle&title=LifeStyle
title注入xss的payload形成xss
2.修复后查找xss
修复后删除了端点访问404
尝试目录爆破发现/test/目录
发现http://samsung.ucweb.com/test/classify.html?dataKey=New&title=
同样存在xss

9. [**存储 Xss 的故事**](https://medium.com/@hossainwalid93/story-of-store-xss-d24c3ab862f0)  
显示名称设置为 TEST”><svg onload=alert(1)// 并创建了帐户  
搜索栏搜索该账户导致xss可惜难以利用  
如果 user1 正在关注 user2，则 user2 将出现在 user1 的搜索栏上可提升利用。  

10. [**Facebook-Instagram CDN 服务器上的 XSS 绕过签名保护**](https://www.amolbaikar.com/xss-on-facebook-instagram-cdn-server-bypassing-signature-protection/)  
CDN 服务器上的所有照片/视频都在 URL 中包含签名,如果我们修改文件扩展名，则会引发错误  
有instagram.fpnq2-1.fna.fbcdn.net. 3599 IN CNAME scontent.xx.fbcdn.net.  
尝试跨域访问  
https://instagram.fpnq2-1.fna.fbcdn.net/v/t51.2885-15/12494762_1700832180174667_9131300789175210564_n.png?_nc_cat=0&oh=cb7024e12c863937b69c3d6c15589697&oe=5B31E89F  
到https://scontent.xx.fbcdn.net/t51.2885-15/12494762_1700832180174667_9131300789175210564_n.html  
形成xss  

11. [**Facebook 收购 Oculus CDN Server 上的 XSS**](https://www.amolbaikar.com/xss-on-facebooks-acquisition-oculus-cdn-server/)  
在“ oculuscdn.com ”上，该错误非常简单明了。只需删除破坏签名验证的“ V ”参数，并且响应包含原始数据。甚至不需要在指向oculus.xx.fbcdn.net的现有CNAME之间进行交换。  
https://scontent.oculuscdn.com/v/t64.5771-25/12401200_1904973622996515_3168267743525841480_n.png?_nc_cat=0&oh=6163326b3eb5e79c16c6949f1e734611&oe=5AD840C8
到https://scontent.oculuscdn.com/t64.5771-25/12401200_1904973622996515_3168267743525841480_n.html  

12. [**Facebook 上的 XSS 通过 PNG 和古怪的内容类型**](https://whitton.io/articles/xss-on-facebook-via-png-content-types/)  
Facebook 上的许多照片/视频现在似乎在 URL 中包含一个哈希（参数oh和__gda__），如果我们修改文件扩展名，这会导致引发错误。  
但幸运的是，广告图片不包含这些参数，修改text/html访问html发现回显  
使用PNG IDAT 块写入payload  
检查是否有任何*.facebook.comDNS 条目指向 CDN发现photo.facebook.com导致xss  
利用facebook的插件结合iframe提取www.facebook.com的csrf令牌  

13. [**我的谷歌名人堂之旅**](https://www.secjuice.com/google-hall-of-fame/)  
搜索谷歌收购业务利用dork：site:*.sidewalklabs.com  
发现一个重定向参数并确认存在重定向  
重定向升级为xss  

14. [**Jotform 和 H1C 私有站点中存储的 XSS 漏洞**](https://www.hackerinside.me/2018/11/critical-stored-xss-vulnerability.html)  
只需在 Name 字段中输入脚本并提交表单。  
当受害者登录他的帐户并检查表单条目或提交时，脚本被执行  