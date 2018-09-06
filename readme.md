To English users:

This is a simple and reliable upgrade solution for password managers( like LastPass).

I'll be happy to write this down in English when I have time :-P





## License

- 本项目的 readme.md 等资源基于 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh)。

  这意味着你可以拷贝、并再发行本项目的内容，但是你将必须同样**提供原作者信息以及协议声明**。同时你也**不能将本项目用于商业用途**，按照我们狭义的理解（增加附属条款），凡是**任何盈利的活动皆属于商业用途**。





## 打造极致的个人密码组管理方案吧！

首先，我们要声明两个公理：

公理一，密码的安全性和密码的长度和构成密码的字符集大小密切相关；

公理二，在公理一的基础之上，密码的安全性和用户的记忆负担呈负相关。即密码越长、越复杂，它的安全性更高，也越不便于用户记忆。



密码的安全性主要是从两个维度进行衡量的：

1. 密码长度。
   - 例如，29位密码的安全性必然要强于9位密码。
2. 所采用密码字符集大小。
   * 采用了字母字符集、数字字符集和特殊符号字符集的密码，它的安全性必然要强于仅使用数字字符集的密码。例如，同样是10位长度的密码，“P5q%t!4^7p” 的安全性必然要强于 "5944624439"。



市面上已有足够好的个人密码管理器，其中著名的有：

* LastPass
* 1Password



无论是 LastPass 还是 1Password，它们都具有极高的安全性和易用性，暴力破解它们需要经受极高难度的考验和巨大时间成本的付出，可以说，将密码保存在这些密码管理器上，已经是足够安全的了。

**但是，它们仍存在一定的隐患。此处我将以 LastPass 为例，对它们的潜在隐患给出系统性的解决方案。**



这是 LastPass：

![01](https://raw.githubusercontent.com/MrWrh/Upgrade_Solution_4_Password_Managers/master/imgs/01.png)

它的隐患主要有两点：

1. LastPass 的密码应具有足够的长度和复杂性，但若是完全满足了它的安全性（长度至少30位，且采用了字母、数字和特殊符号），这样的密码又会超出常人记忆能力的极限。
2. 用户邮箱一旦被攻破，攻击者若是利用它重置密码管理器密码，整个密码组的安全就会陷入危局。



**如何解决？**

早在2013年，微软上线的 Outlook 服务就提供了“别名邮箱”的服务。简而言之，用户可以在主邮箱之外设立别名邮箱，别名邮箱相当于用户同一账号下的另一个名字，它的收发邮件与主邮箱共享，拥有与主邮箱一致的用户体验，只是有一处不同——

> 用户可以在主邮箱和别名邮箱间设置可用于登录的邮箱账号。



![02](https://raw.githubusercontent.com/MrWrh/Upgrade_Solution_4_Password_Managers/master/imgs/02.png)

如图所示，用户除了主邮箱之外，还设置了别名邮箱1与别名邮箱2，两个别名邮箱可以收发邮件，却不能用作登录账号——用别名邮箱登录 Outlook，系统会提示“该 Microsoft 帐户不存在。请输入其他帐户或获取新帐户”的。



我们将别名邮箱设为 LastPass 的登录邮箱：

![03](https://raw.githubusercontent.com/MrWrh/Upgrade_Solution_4_Password_Managers/master/imgs/03.png)

则可以彻底杜绝上文提到的隐患2——即使攻击者得知了你的 LastPass 登录邮箱，他也无从攻击你的登录邮箱，去达到重置密码的目的。



对于隐患一，则有一个很简便的方法：

对于弱密码（长度少于30位），我们可以利用早已成熟的编码算法或加密算法进行处理，得到足够长度的强密码。

![04](https://raw.githubusercontent.com/MrWrh/Upgrade_Solution_4_Password_Managers/master/imgs/04.png)

举一个例子：

这是一条弱密码：

```
001Woshiyiduanmima!
```

利用SHA1加密算法加密后的结果：

```
0011e45623bdf4275ff6a802ad12be4adfefea65
```

我们还可以给它附加后缀码：

```
0011e45623bdf4275ff6a802ad12be4adfefea65$sudoBoom!
```

这样一条常人难以记忆的强密码，已经足够胜任密码管理器的密码了。



现在我们得到了：

![05](https://raw.githubusercontent.com/MrWrh/Upgrade_Solution_4_Password_Managers/master/imgs/05.png)

现在，你的密码组已经拥有了极高的安全性——可见的漏洞大概只剩下用户个人被社工、LastPass 官方被侵入，不过，这样的事件发生的概论极为微小，也属于难于防范的范畴。此外，从破解成本上来讲，也没人会愿意去做这近乎不可能完成的任务。

所以，我们有相当的理由相信，现在的密码组管理方案已经是极为安全的了。



若想继续讨论，欢迎联系：mr.rhwang@gmail.com

