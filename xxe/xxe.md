# XXE
XML外部实体注入(XXE)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**使用本地 DTD 文件利用 XXE**](https://mohemiv.com/all/exploiting-xxe-with-local-dtd-files/)
当基于错误外带利用XXE被防火墙拦截时  
可以利用本地DTD文件进行覆盖利用  
如果您定义两个具有相同名称的实体，则只会使用第一个实体。  

2. [**从盲目的 XXE 到根级文件读取访问**](https://honoki.net/2018/12/12/from-blind-xxe-to-root-level-file-read-access/)
发现响应包回显xml格式，尝试修改ct头post传递错误xml版本和正文，显示报错  
尝试burp的 Collaborator外带测试，发现只收到dns请求，http请求被防火墙过滤  
通过回显发现盲xxe，结合github发现的内部服务可能存在jira的ssrf漏洞  
发现传入http请求，随后结合外部实体调用回显本地文件  
使用:绕过/etc/passwd显示不全  
<!ENTITY % ent "<!ENTITY data SYSTEM ':%file;'>">  

3. [**Prince v10 及以下版本中的 XSS 到 XXE (CVE-2018-19858)**](https://www.corben.io/XSS-to-XXE-in-Prince/)  
Prince，这是一种将“HTML、XHTML 或许多基于 XML 的文档格式之一”转换为 PDF 的软件。  
由于存在xss导致可通过pdf生成xxe泄露本地文件数据  
<iframe src="http://<server>/xxe.xml">  

4. [**SAP 中一个有趣的 XXE**](https://medium.com/@zain.sabahat/an-interesting-xxe-in-sap-8b35fec6ef33)  
发现一个POST请求/sap/cpa/api/getSolutions传递了XML  
修改payload发现回显  
修改为/etc/passwd发现漏洞。  