# LFD
本地文件读取(LFD)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**以 17,000 美元阅读 ASP 机密**](https://samcurry.net/reading-asp-secrets-for-17000/)  
发现任意文件读取https://domain.com/utility/download.aspx?f=file1234.docx  
读取download.aspx成功，使用fuzz绕过..的限制，GET /utility/download.aspx?  f=.[fuzz]./utility/download.aspx  
最后.+.替代..绕过，.+./.+./bin/redacted.dll读取，.+./.+./web.config证明危害  