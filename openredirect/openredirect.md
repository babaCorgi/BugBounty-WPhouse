# OpenRedirect
开放重定向(OpenRedirect)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**[开放重定向] 开发人员很懒（或者可能很忙）**](https://infosecwriteups.com/open-redirect-developers-are-lazy-or-maybe-busy-6c51718b10e4)  
account/login?next=https://www.google.com利用基本@，//尝试失败，  
尝试使用HPP，发现跳转https://www.example.com/www.google.com说明参数污染成功  
于是使用@google.com进行第二参数污染，成功跳转但是重复案例  
开阔思维使用注册接口/account/signup?next=同样操作，未重复且未修复  