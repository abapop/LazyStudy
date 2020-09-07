## 当前程序版本：2.6.9 （fork更新）
##理论上数据库加上options字段，逻辑更清晰，但是这样一改，getanswer函数需要改动，所以折中了一下，使用“题干+选项”来搜题，不用改源代码这么多。
- 修改网络题库更新，更新timu包括题干和选项；
- 修改getScores函数，通过“学分明细”获取明确学分；
- 修改挑战答题中，获取题库答案，使之通过“题干+选项”进行搜题，确保能找到正确答案（使用前请更新题库，确保题库的question带选项字符串）；
- 修改文章和视听学习内容，通过收藏更新判断是否重复的逻辑，现在可以一次正确，不会出现文章或视频学习个数不够的情况；
- 其它小修改若干……

## 当前程序版本：2.6.9
**现在满分为42哦(除了每日和专项答题)**  
因为刚刚上线，所以`commit`有点多，更新也比较频繁，经常是想到哪改到哪，所以请多包涵，有问题可以提`issue`    
  
## 使用说明
- 因为部分模块有随机性，所以控制台输出的数量和时间不一定准确。  
- 文章和视频：点击“切到 强国”，在强国主界面点击“开始浏览”，即可自动浏览，**并且会记录已阅读的文章到数据库，重复阅读会自动退出**。
- 挑战答题：进入挑战答题界面，点击“挑战答题”，开始答题，答错会自动重新开始，得到6分停止。
- 每日答题：进入每日、专项、每周界面，点击"每日答题等"。程序会自行进行答题，得到6分停止。
- 手动改题：手动查改删增，支持以题目或答案关键字查询，或列出最后十条入库记录  
- 题库页面有清空文章列表的功能，方便两个账号的用户使用
- 更新网络题库：从网络同步最近题库，过滤后入tikuNet表  
# 懒人学习

一款基于auto.js，安卓自动学习脚本，支持看文章视频、收藏分享评论、挑战答题、每日答题、每周答题。  
本项目仅供autojs交流学习，请勿用于商业

[release下载](https://github.com/lolisaikou/LazyStudy/releases/)  
## 关于本脚本
因原作者将脚本被删除，这里只能依靠本人能力和[ivanwhaf](https://github.com/ivanwhaf/xxqg-helper)的脚本更新  

## 软件界面
<div align="center">
<img src="https://ftp.bmp.ovh/imgs/2020/06/bfecded9b5fb510b.jpg" height="30%" width ="30%" />
<img src = 'https://ftp.bmp.ovh/imgs/2020/06/beb751a02940ceb9.jpg' height="30%" width ="30%" />
</div>


## 环境依赖

- 手机为安卓7.0以上版本
- 安装程序后，点击加载悬浮窗，弹出授权界面。请授权 无障碍 和 悬浮窗。


## 版本更新  
- 2020.08.27  
        重构了题库更新的方法，不再使用jsoup来解析[原题库](http://49.235.90.76:5000/)，而是使用js自带的方法来解析题库的[json源](http://49.235.90.76:5000/api/questions)。并且使用了[jsDelivr](https://www.jsdelivr.com/)加速了json源，[加速用](https://github.com/lolisaikou/tiku-autoupdate)的项目在这里。 [#40](https://github.com/lolisaikou/LazyStudy/issues/40)  
        ~~大概~~修复看视频出现的问题 [#42](https://github.com/lolisaikou/LazyStudy/issues/42)  
***
- 2020.08.21  
        修复了上个版本的报错(~~因为太懒直接复制粘贴另一个版本的代码~~)  
        题库页面增加了清空文章列表的按钮，方便有两个账号的用户使用  
        为文章阅读增加了一个循环，直到循环次数大于3次或阅读文章满分停止  
        为配合上面的功能，对获取积分和阅读文章的模块做了相应调整  
        调整随机背景的透明度  
***
- 2020.08.16  
        主页增加随机背景 [#29](https://github.com/lolisaikou/LazyStudy/issues/29)  
        为部分函数增加了随机性（提高安全性）  
        ~~大概~~修复听广播卡住的问题 [#27](https://github.com/lolisaikou/LazyStudy/issues/27)  
        现在更新题库会正常显示更新了多少道题(不会再显示更新了undefined道题) [#20](https://github.com/lolisaikou/LazyStudy/issues/20)  
        修改学习顺序,减少不必要的流程  
***
- 2020.08.14  
        跟进了最新版的积分规则  
        修复一些小问题  
        增加一个没用的功能  
        下面总结一下变化  

|原项目|变化|现项目|现分数|
| :-: | :-: | :-: | :-: |
|登录|不变|×|1|
|阅读文章|与文章学习时长合并|我要选读文章|6|
|文章学习时长|与阅读文章合并(且2分钟1分改为1分钟1分)|我要选读文章|6|
|视听学习|不变|×|6|
|视听学习时长|1分钟1分(原2分钟1分)|×|6|
|每日答题|10道题减为5道|×|6|
|挑战答题|10道题减为5道|×|6|
|订阅|不变|×|2|
|收藏|删除|×|0|
|分享|不变|×|1|
|评论|次数-1|×|1|
|本地频道|不变|×|1|
|**合计**|||42|
***
- 2020.08.11  
        点击文章的方式从点击页面上的日期换到控件了  
        因为autojspro最新版有bug，需要降级，所以原来的签名丢失，所以**本次更新需要卸载**（记得备份文章列表）  
        更新了题库  
        听广播时间增加了1分钟（防止分数不够）  
        修改听广播部分的逻辑  
        修复订阅部分的问题  
        增加了运行结束后停止收听广播的功能
        因为影响阅读文章，所以将看小视频和本地频道到**最后（收听完广播才会运行）**  
***
- 2020.07.26  
        修复因为首页没有当天新闻，出现的控制台被刷屏，无法继续阅读文章的问题  
        解决文章学习时长不够，但剩余文章为0不能阅读的问题  
        增加了判断当前是否在答题界面的功能，防止直接报错停止  
        修复了一些小问题  
***
- 2020.07.20  
        增加了选择文章学习类别的功能 [#11](https://github.com/lolisaikou/LazyStudy/issues/11)  
        修复如果文章标题里有英文单引号会导致数据库写入错误的问题  
        更改了阅读文章部分的逻辑，把视频检测的部分放在了获取文章标题的前面  
        增加了文章标题获取的方法，感谢[#issuecomment-660916041](https://github.com/lolisaikou/LazyStudy/issues/11#issuecomment-660916041)  
        修复了一些小问题  
***
- 2020.07.08  
        现在每日答题功能可以答每周和专项答题了  
        修复上个版本留下来的小bug  
***
- 2020.07.07  
        将已学习的文章存储到**其他数据库**内而不是`题库`（备份题库的功能也换为备份已读文章的数据库）  
        修改每日浏览逻辑，解决运行结束，"视听学习"分数不够的问题  
        ~~可能~~修复 [#3](https://github.com/lolisaikou/LazyStudy/issues/3) 中提到的问题  
        修改限制每日挑战答题次数的逻辑  
        修复订阅强国号的各种问题  
***
- 2020.06.26  
        继续修复听广播卡住的问题  
        增加每日运行结束后自动备份题库（备份到/sdcard/Download/下）  
        修复一些小问题  
***
- 2020.06.21  
        修复卡在听广播页面的问题（其实是卡在订阅部分了，因为在非主页的情况下，click方法找不到订阅这这个控件）  
        修改每日浏览逻辑，降低了浏览的时间  
***
- 2020.06.20  
        **增加了导入、导出题库的功能，方便更新（更新时一定要到题库页面导出题库）**  
        修复了阅读到重复文章会增加计数的问题  
        合入订阅(实验性)功能到主程序中(会在浏览中自动订阅)
***
- 2020.06.19  
        完全依靠[ivanwhaf](https://github.com/ivanwhaf/xxqg-helper)的脚本，恢复了使用  
        修复了大部分功能无法使用的问题  
        ~~每日答题功能不能做每周和专项答题了~~7月8日更新已支持  
        挑战答题答错会自动重新挑战，而且增加了限制，每日最多10题，达到自动停止  
        每日答题答够十题也会自动返回了  
        每日阅读的文章自动添加到数据库，重复阅读会自动返回，感谢[wanghuisenior](https://github.com/wanghuisenior)  
        更改包名为com.lazyxue（因为使用auto.js pro打包导致和之前的签名不同）  
        增加了订阅功能，感谢[colincai](https://github.com/ivanwhaf/xxqg-helper/issues/75)(20日更新已合入)~~（未测试稳定性，未实装，感兴趣可以下载subscribe.js在学习强国主页运行即可）~~  
***
        
- 2020.04.02  
        再次修复填空题获取不到题目问题  
***
- 2020.04.01  
        修复填空题获取不到题目问题  
***
- 2020.03.27  
        修复每日答题填空题获取多个空格时错误；获取正确答案由滑屏改控件滚动  
***
- 2020.03.21  
        修复获取填空题题目失败，点击评论后增加停顿  
***
- 2020.02.23  
        重制界面，新增按积分浏览，修复改题中update语句错误  
        支持按题目与答案模糊搜索，增加在线帮助与更新功能    
        挑战答题点击间隔改为随机  
***
- 2020.01.19  
        新增下载网络题库到本地，取消切换小程序方式(感谢kessil)    
        修复每日答题,错误答案入库问题    
        更新浏览文章视频部分，目前为xxqg_v3.1.0 (无 UI).js(感谢ivanwhaf)    
        新增手动查改删增题库功能    
        新增本地频道浏览    
***
- 2019.12.24  
        修复每日答题获取提示内容失败等问题    
***
- 2019.12.15  
        修复答题部分bug 取消浏览时收藏评论分享功能(避免部分手机报错)    
***
- 2019.12.13  
        重构收藏分享评论模块，修复错误    
***
- 2019.12.11  
        重构每日答题逻辑，速度更快    
***
- 2019.12.08  
        新增每日答题功能    
***
- 2019.11.21  
        发布    

## **特别感谢**
###### 以下排名不分先后  
>[**lgpersonal**](https://github.com/lgpersonal/)  
>[**kessil**](https://github.com/kessil/AutoXue)  
>[**ivanwhaf**](https://github.com/ivanwhaf/xxqg-helper)  
>[**studyhelperhelper**](https://github.com/studyhelperhelper/studyhelper)  
