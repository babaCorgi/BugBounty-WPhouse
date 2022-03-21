# LogicFlaw
逻辑漏洞(LogicFlaw)案例合集  
仅供参考
## :ledger: 索引及其简述
1. [**Facebook 页面评论中的不可移除标签**](https://medium.com/@maxpasqua/unremovable-tags-in-facebook-page-reviews-656e095e69aa)  
发表帖子评论并标记受害者，受害者无法删除标签  
这背后的影响是受害者被永久卡住  

2. [**使用格式错误的时间打破约会和工作面试时间表**](https://medium.com/@maxpasqua/breaking-appointments-and-job-interview-schedules-with-malformed-times-edef103e46ba)  
点击工作申请并点击日程安排面试  
拦截graphql查询，将建议的结束时间更改为格式错误的时间，例如15393834250000  
会议日历和工作面试时间表造成不可逆转的损害，无法访问。  

3. [**链接两个漏洞以第二次打破 Facebook 预约时间**](https://medium.com/@maxpasqua/chaining-two-vulnerabilities-to-break-facebook-appointment-times-for-the-second-time-ac639f8c8773)  
点击更改可用的预约时间  
编辑 end_times 和 start_times 参数使其匹配(缺陷一)  
将 max_advanced_notice 参数编辑为格式错误/更大的时间（例如 15552000000）  
会议日历和工作面试时间表造成不可逆转的损害，无法访问。  

4. [**令牌蛮力到帐户接管到特权升级到组织接管**](https://infosecwriteups.com/token-brute-force-to-account-take-over-to-privilege-escalation-to-organization-take-over-650d14c7ce7f)  
管理员邀请外部用户链接为https://login.redacted.com/accounts/?service=product&digest=saaOBeXStZDRqgVlSRPAgPSY0  
但邀请已经存在账号的用户为https://product.redacted.com/invitations?inviteId=160000002637191&type=accept&source=mail  
无签名无hash且使用后仍然不过期，通过爆破可不受邀请就加入组织  

5. [**Facebook WhiteHat：即使在离开小组后也能访问小组计划的详细信息**](https://whitehatfamilyguy.blogspot.com/2018/12/able-to-access-facebook-group-plan-even.html)  
对于群组内用户ABC，当B退出后，B仍然可以查看到原组内的计划更改等等更新信息  

6. [**在 Google Pay 上绕过刮刮卡**](https://medium.com/@pratheesh.p.narayanan/bypassing-scratch-cards-on-google-pay-8915d5423385)
一旦有人注册了该服务，您将在您的Google Pay上获得一张刮刮卡。您可以在优惠期间获得多达30张卡  
可以通过使用虚拟号码绕过,在不推荐任何人的情况下获得 30 张刮刮卡.  