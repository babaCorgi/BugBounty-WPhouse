# RCE
远程代码执行(RCE)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**从寻找笔记本电脑到寻找远程代码执行**](https://medium.com/@aniltom/from-hunting-for-a-laptop-to-hunting-down-remote-code-execution-72cce2761846)
发现http://stw.asus.com/子域名403且显示iis服务器5.30  
通过WEBDEV的远程代码执行漏洞进行RCE（CVE-2017-7269）  

2. [**nokia.com 中的 RCE**](https://medium.com/@sampanna/rce-in-nokia-com-59b308e4e882)  
通过yandex发现子域http://emop.ext.net.nokia.com  
使用https://suip.biz/在线扫描发现老版本drupal  

3. [**Facebook 服务器上的远程代码执行**](https://blog.scrt.ch/2018/08/24/remote-code-execution-on-a-facebook-server/)  
sentryagreements.thefacebook.com域使用Sentry日志应用采用Django框架编写  
调试信息为关闭导致env泄露，通过分析发现可以用任意 pickle 内容伪造我们自己的 cookie  
编写POC获取现有sentrysid cookie 的内容，并将其内容替换为在反序列化时将运行os.system(“sleep 30”)的任意对象  

4. [**Hubspot 中的 RCE 与 HubL 中的 EL 注入**](https://www.betterhacker.com/2018/12/rce-in-hubspot-with-el-injection-in-hubl.html)  
{{7*7}} 返回了'49'  
{{'a'.getClass()}}返回java.lang.String  
通过{{'a'.getClass().forName('javax.script.ScriptEngineManager').newInstance().getEngineByName('JavaScript').eval(\"var x=new java.lang.ProcessBuilder; x.command( \\\"netstat\\\"); org.apache.commons.io.IOUtils.toString(x.start().getInputStream())\")}}  
获取RCE  

5. [**GitHub 桌面 RCE (OSX)**](https://0xacb.com/2018/12/04/github-desktop-rce/)  
打开文件在github客户端这个功能  
x-github-client://openRepo/https://github.com/github/training-kit?branch=master&filepath=README.md  
filepath路径劫持../../../../../../../../../../../Applications/Calculator.app导致打开计算器  

6. [**深入研究 SCP 命令注入**](https://dylankatz.com/digging-in-to-scp-command-injection/)  
对于SCP命令scp -f /some/user/provided/path可被路径劫持  
如path为/; touch /tmp/foo  
劫持为scp -f /; touch /tmp/foo  
形成命令注入  