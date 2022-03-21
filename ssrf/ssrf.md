# SSRF
服务端请求伪造(SSRF)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**OpenID 支持中的服务器端请求伪造**](https://medium.com/@putracraft.theworld/server-side-request-forgery-in-openid-support-defcc64d5e41)  
当更改照片配置文件时发现重定向  
添加http://127.0.0.1:31337发现回显协议错误  

2. [**像老板一样利用 SSRF — 将 SSRF 升级为本地文件读取！**](https://medium.com/@zain.sabahat/exploiting-ssrf-like-a-boss-c090dc63d326)  
通过反向ip查找到子域名https://help.redacted.com,发现正在允许jira  
确认存在jira的ssrf漏洞  
访问127.0.0.1发现运行GlassFish服务  
查找到GlassFish的Nday并进行payload的url双重编码获取本地文件读取  
