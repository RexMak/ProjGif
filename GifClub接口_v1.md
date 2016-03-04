---

<span id = "1"></span>

# 1. 手机注册

http://1.gifclub.applinzi.com/index.php/Home/index/phoneregister

请求体格式：字符串

|请求参数	|参数说明	|
|--- 		|---		|
|phoneno 	|手机号码	|
|pwd		|密码		|
|nickname	|昵称		|

返回格式：JSON

|返回参数	|参数说明		|
|--- 		|---			|
|errno		|错误代码		|
|msg/info	|信息描述		|

---

<span id = "2"></span>

# 2. 手机登录

http://1.gifclub.applinzi.com/index.php/Home/index/phonenologin

请求体格式：字符串

|请求参数	|参数说明	|
|--- 		|---		|
|phoneno 	|手机号码	|
|pwd		|密码		|

返回格式：JSON

|返回参数		|参数说明		|
|--- 			|---			|
|errno			|错误代码		|
|info			|用户详细信息	|<span id = "userinfo"></span>
|email			|邮箱地址		|
|headpicture	|头像URL		|
|bgpicture		|用户个性背景图URL|
|nickname		|昵称			|
|phoneno		|手机号码		|
|pwd			|密码（MD5）	|
|qq_tocken		|QQ令牌			|
|sex			|性别（0=男）	|
|sina_tocken	|新浪微博令牌	|
|userid			|用户id			|
|weixin_tocken	|微信令牌		|

---

# 3.邮箱注册与登录

邮箱注册：http://1.gifclub.applinzi.com/index.php/Home/index/emailregister

邮箱登录：http://1.gifclub.applinzi.com/index.php/Home/index/emaillogin

请求体格式及参数，参照[手机注册](#1)和[手机登录](#2)，将phoneno参数改为email参数即可。

---

# 4.上传用户头像

http://1.gifclub.applinzi.com/index.php/Home/index/uploadheadpicture

请求体格式：表单

|请求参数	|描述		|
|---		|---		|
|userid 	|用户id		|
|photo  	|头像图片，png/jpg/jpeg/gif格式，不超过50KB|

返回格式：JSON

|返回参数	|描述		|
|---		|---		|
|errno		|错误代码	|
|headurl	|头像图片URL|
|msg		|消息描述	|

---

# 5.修改个性背景图片

http://1.gifclub.applinzi.com/index.php/Home/index/uploadsettingbgpicture

请求体格式：表单

|请求参数	|描述		|
|---		|---		|
|userid 	|用户id		|
|photo  	|头像图片，png/jpg/jpeg/gif格式，不超过50KB|

返回格式：JSON

|返回参数	|描述		|
|---		|---		|
|errno		|错误代码	|
|bgpicture	|头像图片URL|
|msg		|消息描述	|

---

# 6.发布GIF图片

http://1.gifclub.applinzi.com/index.php/Home/index/publishgif

请求体格式：表单

|请求参数	|描述			|
|---		|---			|
|ownerid	|用户id			|
|gifname	|GIF图片，不超过3MB|
|text		|图片描述		|


返回格式：JSON

|返回参数	|描述		|
|---		|---		|
|errno		|错误代码	|
|msg		|消息描述	|<span id = "info"></span>
|info		|本条发布的详细信息|
|commentsno	|评论数量		|
|createtime |图片创建时间	|
|gifurl		|GIF图片的URL	|
|likesno	|点赞数量		|
|newsid		|该条记录的id	|
|ownerid	|发布者的id		|
|text		|描述文字		|
|user		|[发布者详细信息](#userinfo)	|

---

# 7.获取所有用户GIF图记录
http://1.gifclub.applinzi.com/index.php/Home/index/publicnewslist

请求体格式：字符串

|请求参数	|参数说明			|
|--- 		|---				|
|userid 	|当前登录的用户id	|
|precount	|跳过开头记录的数量	|
|count		|请求记录的数量		|

返回格式：JSON

|返回参数	|参数说明		|
|--- 		|---			|
|errno		|错误代码		|
|msg		|用户发布[记录的详细信息](#info)列表|

---

# 8.获取某个用户的所有GIF发布记录

http://1.gifclub.applinzi.com/index.php/Home/index/personalnewslist

请求体格式：字符串

|请求参数		|参数说明			|
|--- 			|---				|
|curuserid		|当前登录的用户id	|
|otheruserid	|要查看的用户id		|
|precount		|跳过开头记录的数量	|
|count			|请求记录的数量		|

注意：如果看当前登录的用户发布的所有GIF，则otheruserid和curuserid相同即可

返回格式：JSON

|返回参数	|参数说明		|
|--- 		|---			|
|errno		|错误代码		|
|msg		|用户发布[记录的详细信息](#info)列表|

---

# 9.对记录进行点赞

http://1.gifclub.applinzi.com/index.php/Home/index/zan

请求体格式：字符串

|请求参数		|参数说明			|
|--- 			|---				|
|newsid			|要点赞的记录的id	|
|userid			|当前登录的用户id	|

返回格式：JSON

|返回参数	|参数说明	|
|--- 		|---		|
|errno		|错误代码	|
|msg		|响应信息	|

---

# 10.获取某记录被点赞的列表

http://1.gifclub.applinzi.com/index.php/Home/index/zanlist

请求体格式：字符串

|请求参数		|参数说明			|
|--- 			|---				|
|newsid			|要查看点赞列表的记录的id|
|page			|列表页数，从1开始|

返回格式：JSON

|返回参数	|参数说明	|
|--- 		|---		|
|errno		|错误代码	|
|info		|点赞过的[用户详细信息](#info)列表	|


---

# 11.对记录进行评论

http://1.gifclub.applinzi.com/index.php/Home/index/uploadcomment


请求体格式：字符串

|请求参数		|参数说明			|
|--- 			|---				|
|newsid			|要评论的记录的id	|
|userid			|当前登录的用户id	|
|text			|评论的内容			|

返回格式：JSON

|返回参数	|参数说明	|
|--- 		|---		|
|errno		|错误代码	|
|msg		|响应信息	|