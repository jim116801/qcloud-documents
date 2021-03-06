## 1.接口描述
登录保护接口提供恶意登录识别、撞库行为识别等能力，根据用户的账号、信用和登录行为来源判断当次登录的恶意等级
<br> 协议：HTTPS
<br> 域名：csec.api.qcloud.com
<br> 接口名：LoginProtection

## 2.输入参数
以下请求参数列表仅列出了接口请求参数，正式调用时需要加上公共请求参数，见[公共请求参数](https://www.qcloud.com/doc/api/254/1778)页面。
<br> 其中，此接口的Action字段为LoginProtection。
<table class="t">
<tbody><tr>
<th> <b>参数名称</b>
</th><th> <b>是否必须</b>
</th><th> <b>类型</b>
</th><th> <b>描述</b>
</th></tr>
<tr>
<td> loginIp
</td><td><font color=red> 必选 </font color=red>
</td><td> String
</td><td> 登录来源的外网IP
</td></tr>
<tr>
<td> loginTime
</td><td><font color=red> 必选 </font color=red>
</td><td> UInt
</td><td> 登录时间戳，单位秒
</td></tr>

<tr>
<td> accountType
</td><td><font color=red> 必选 </font color=red>
</td><td> UInt
</td><td> 用户账号类型
<br> 0：其他账号
<br> 1：QQ开放帐号
<br> 2：微信开放帐号
<br> 4：手机号
<br> 6：手机动态码
<br> 7：邮箱
</td></tr>
<tr>
<td> uid
</td><td> <font color=red> 必选 </font color=red>
</td><td> String
</td><td> 用户ID
<br> accountType不同对应不同的用户ID。如果是QQ或微信用户则填入对应的openId
</td></tr>
<tr>
<td> appId
</td><td> 可选
</td><td> String
</td><td> accountType是QQ或微信开放账号时，该参数必填，表示QQ或微信分配给给网站或应用的appId，用来唯一标识网站或应用
</td></tr>
<tr>
<td> associateAccount
</td><td> 可选
</td><td> String
</td><td> accountType是QQ或微信开放账号时，用于标识QQ或微信用户登录后关联业务自身的账号ID
</td></tr>
<tr>
<tr>
<td> nickName
</td><td> 可选
</td><td> String
</td><td> 昵称，utf8编码
</td></tr>
<td> phoneNumber
</td><td> 可选
</td><td> String
</td><td> 手机号；国家代码-手机号，如0086-15912345687. 注0086前不需要+号
</td></tr>
<tr>
<td> emailAddress
</td><td> 可选
</td><td> String
</td><td> 用户邮箱地址（非系统自动生成）
</td></tr>
<tr>
<td> registerTime
</td><td> 可选
</td><td> UInt
</td><td> 注册时间戳，单位秒
</td></tr>
<tr>
<td> registerIp
</td><td> 可选
</td><td> String
</td><td> 注册来源的外网IP
</td></tr>
<tr>
<td> passwordHash
</td><td> 可选
</td><td> String 
</td><td> 用户密码进行2次hash的值，只要保证相同密码hash值一致即可
</td></tr>
<tr>
<td> cookieHash
</td><td> 可选
</td><td> String
</td><td> 用户Http请求中的cookie进行2次hash的值，只要保证相同cookie的hash值一致即可
</td></tr>
<tr>
<td> loginSource
</td><td> 可选
</td><td> UInt
</td><td> 登录来源
<br> 0：其他
<br> 1：PC网页
<br> 2：移动页面
<br> 3：APP
<br> 4：微信公众号
</td></tr>
<tr>
<td> loginType
</td><td> 可选
</td><td> UInt
</td><td> 登录方式
<br> 0：其他
<br> 1：手动帐号密码输入
<br> 2：动态短信密码登录
<br> 3：二维码扫描登录
</td></tr>
<tr>
<td> referer
</td><td> 可选
</td><td> String
</td><td> 用户Http请求的referer值
</td></tr>
<tr>
<td> jumpUrl
</td><td> 可选
</td><td> String
</td><td> 登录成功后跳转页面
</td></tr>
<tr>
<td> userAgent
</td><td> 可选
</td><td> String
</td><td> 用户Http请求的userAgent
</td></tr>
<tr>
<td> xForwardedFor
</td><td> 可选
</td><td> String
</td><td> 用户Http请求中的x_forward_for
</td></tr>
<tr>
<td> mouseClickCount
</td><td> 可选
</td><td> UInt
</td><td> 用户操作过程中鼠标点击次数
</td></tr>
<tr>
<td> keyboardClickCount
</td><td> 可选
</td><td> UInt
</td><td> 用户操作过程中鼠标点击次数
</td></tr>
<tr>
<td> result
</td><td> 可选
</td><td> UInt
</td><td> 登录结果
<br> 0：失败
<br> 1：成功
</td></tr>
<tr>
<td> reason
</td><td> 可选
</td><td> UInt
</td><td> 失败原因
<br> 0：其他
<br> 1：帐号不存在
<br> 2：密码错误
<br> 3：参数错误 未按要求填写数据
<br> 4：验证错误
</td></tr>
<tr>
<td> loginSpend
</td><td> 可选
</td><td> UInt
</td><td> 登录耗时，单位秒
</td></tr>
<tr>
<td> macAddress
</td><td> 可选
</td><td> String
</td><td> mac地址或设备唯一标识
</td></tr>
<tr>
<td> vendorId
</td><td> 可选
</td><td> String
</td><td> 手机制造商ID，如果手机注册，请带上此信息
</td></tr>
<tr>
<td> appVersion
</td><td> 可选
</td><td> String
</td><td> APP客户端版本
</td></tr>
<tr>
<td> imei
</td><td> 可选
</td><td> String
</td><td> 手机设备号
</td></tr>
<tr>
<td> businessId
</td><td> 可选
</td><td> UInt
</td><td> 业务ID
<br> 网站或应用在多个业务中使用此服务，通过此ID区分统计数据
</td></tr>
</td></tr></tbody></table>

## 3.输出参数
<table class="t">
<tbody><tr>
<th> <b>参数名称</b>
</th><th> <b>类型</b>
</th><th> <b>描述</b>
</th></tr>
<tr>
<td> Nonce
</td><td> UInt
</td><td> 随机正整数，与 Timestamp 联合起来, 用于防止重放攻击（公共参数）
</td></tr>
<tr>
<td> loginIp
</td><td> String
</td><td> 登录IP
</td></tr>
<tr>
<td> loginTime
</td><td> String
</td><td> 登录时间
</td></tr>
<tr>
<td> uid
</td><td> String
</td><td> 用户ID，accountType不同对应不同的用户ID。如果是QQ或微信用户则填入对应的openId
</td></tr>
<tr>
<td> associateAccount
</td><td> String
</td><td> accountType是QQ或微信开放账号时，用于标识QQ或微信用户登录后关联业务自身的账号ID
</td></tr>
<tr>
<td> message
</td><td> String
</td><td> 模块错误信息描述，与接口相关
</td></tr>
<tr>
<td> level
</td><td> Int
</td><td> 0：表示无恶意<br>1～4：恶意等级由低到高
</td></tr>
<td> code
</td><td> Int
</td><td> 公共错误码，0表示成功，其他值表示失败。详见错误码页面的<a href="https://www.qcloud.com/doc/api/254/1781"target="black">公共错误码</a>
</td></tr>
</tbody></table>

## 4.示例代码
代码下载：  [Python示例](https://mc.qcloudimg.com/static/archive/de08cb326ab99b568664b2bb7c269f4e/LoginProtection.py.zip) [PHP示例](https://mc.qcloudimg.com/static/archive/2a728e6e88889ae9082d596288505cfd/LoginProtection.php.zip) [Java示例](https://mc.qcloudimg.com/static/archive/db5e010d2ab0070fe8b4f08e3a71238b/LoginProtection.java.zip) [.Net示例](https://mc.qcloudimg.com/static/archive/8773908b78df5570f45d3b2a7d25cbfc/LoginProtection.cs.zip)
<br> 一个完整的请求需要两类请求参数：公共请求参数和接口请求参数。这里只列出了接口请求参数，并未列出公共请求参数，有关公共请求参数的说明可见[公共请求参数](https://www.qcloud.com/doc/api/254/1778)小节。
<pre>
请求示例 ：
https://csec.api.qcloud.com/v2/index.php?
Action=LoginProtection
&<a href="https://www.qcloud.com/doc/api/229/6976">公共请求参数</a>
&secretId=AKIDmQtAxYTAB2iBS8s2DCzazCD2g7OUq4Zw
&accountType=1
&uid=D692D87319F2098C3877C3904B304706
&loginIp=127.0.0.1
&loginTime=11254
&associateAccount="SpFsjpyvaJ27329"
</pre>

## 5.响应示例
```
{
"code": 0,
"message": "No Error",
"level": 0,
"loginIp": "121.14.96.121",
"loginTime": 1436673889,
"uid": "00000000000000000000000033121475",
"associateAccount": "SpFsjpyvaJ27329"
}　
```