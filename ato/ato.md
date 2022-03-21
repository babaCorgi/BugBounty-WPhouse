# ATO
账户接管(ATO)案例合集  
仅供参考
## 索引及其简述
1. [**价值 800 万印尼盾的 Tokopedia 账户接管漏洞**](https://ironfisto.medium.com/tokopedia-account-takeover-bug-worth-8-million-idr-5474cb5b5cc9)  
重置密码处输入受害者密码获取重置链接
https://accounts.tokopedia.com/otp/c/page?otp_type=132& email=ezgcmmfgc%40champmails.com&ld=https://account s.tokopedia.com/resetpassword?e=ZXpnY21tZmdjQGNoYW1wbWFpbHMuY29t  
添加&otpcode=000000实现了账户接管

2. [**#BugBounty —“用户帐户接管-我只需要您的电子邮件 ID 即可登录您的购物门户帐户”**](https://logicbomb.medium.com/bugbounty-user-account-takeover-i-just-need-your-email-id-to-login-into-your-shopping-portal-7fd4fdd6dd56)
第三方oauth2登录，某post包只验证回调token或emailID中的一个  
导致emailID越权从而登录他人账户。  

3. [**影响 4 亿用户的 Microsoft 帐户接管漏洞**](https://www.safetydetectives.com/blog/microsoft-outlook/)  
1.success.office.com的子域接管  
success.office.com的 CNAME 记录指向 successcenter-msprod.azurewebsites.net  
能够通过注册名为 successcenter-msprod 的 Azure Web 应用程序来接管子域。(CNAME)  
2.不正确的 OAuth 检查  
Microsoft Outlook、Store 和 Sway等等域下的OAuth回调错误配置允许信任 *.  office.com 通配符子域名  
结合之前的子域接管可实现单点击窃取用户的回调token  

4. [**在 Android 应用程序上完成用户帐户接管**](https://gauravnarwani.com/android-acc-takeover/)  
1.OTP 绕过导致完全账户接管  
响应码出现在响应包  
2.其他用户无交互更改密码  
密码重置页面隐藏在后台  
POST /api/update_password?password=password&mobile=XXXXXXXXXX  
密码不做验证。  

5. [**帐户接管的爱情故事（链接主机标头注入接管某人的帐户）**](https://chainlover.blogspot.com/2018/11/love-story-of-account-takeover-chaining.html)  
发现主机头注入重定向X-Forwarded-Host: evil.com   
结合重置密码后登录的redirect_to_referer=yes  
重定向到“ evil.com/reset?token=abc ”导致token被劫持  