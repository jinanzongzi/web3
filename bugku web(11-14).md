<h2>bugku web(11-14）</h2>
11.先查看了源码，没看出什么，看了wp发现需要后台扫描，下不到扫描工具，看到响应是shell.php，然后要用burp爆破密码，第一次学了下，没太搞明白。后来朋友给发了御剑。<br>
12.源码里面有base64编码，解码出密码，登录说ip被禁止，说是要用xff修改地址X-Forwarded-For:127.0.0.1<br>
13.描述是看看源码，查看源码，发现有url编码，解码后得到一个flag提交是错误的，忘记页面还有一个输入框，试着输入这个flag，得到真正的flag<br>
14.点击check出来index.php评论说是php伪协议，不懂，看了答案**（上面   ?file=php://filter/read=convert.base64-encode/resource=index.php  的含义
?file是一个get参数传递，php://可以看出是一种协议名称，php://filter/是一种访问本地文件的协议，/read=convert.base64-encode/表示读取的方式是base64编码后，resource=index.php表示目标文件为index.php。）**出来一个base64编码，解码后得到flag