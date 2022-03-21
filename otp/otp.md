# OTP/2FAbypass
OTP绕过(OTP/2FAbypass)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**密码重置中的错误配置故事**](https://footstep.ninja/posts/password-reset/)  
响应包出现了auth_token导致账户接管  
重置链接为https://[team_name].redacted.com/Auth/ResetPassword/[auth_token]。  

2. [**客户端验证再次来袭：PIN 码绕过！（APP）**](https://www.randorisec.fr/client-side-validation/)  
某银行应用每次启动都需要pin码，通过frida发现程序只做客户端验证，拦截返回值并始终为1实现绕过  

3. [**Instagram 多重身份验证绕过**](https://medium.com/@vishnu0002/instagram-multi-factor-authentication-bypass-924d963325a1)  
使用 facebook business中的添加 instagram 帐户功能可以绕过双重身份验证。  
在将受害者帐户与攻击者 Facebook 帐户合并时，受害者帐户的 2FA 会自动绕过，  
攻击者使用启用 2FA 的受害者帐户而不进入 2FA 进程  
