# ShareSDK的使用 #
[官网](http://www.mob.com)

[Demo地址](https://github.com/uncleleonfan/ShareSDKDemo)

测试QQ号：3409609054 szdhm666 

# 集成步骤 #

## 1. 申请AppKey ##
[如何在mod创建应用](http://bbs.mob.com/forum.php?mod=viewthread&tid=8212)

测试用AppKey 17a2846dca760

## 2. 下载SDK ##

[下载SDK](http://www.mob.com/#/downloadDetail/ShareSDK/android)

## 3. 快速集成 ##
[Android Studio集成](http://bbs.mob.com/forum.php?mod=viewthread&tid=22130)


### 注意 ###
QQ的回调intent，实现QQ的分享必须要添加，并且保证您assets下的sharesdk.xml里配置的QQ的appid与这里的tencent后面的appid保持一致，否则QQ分享是没有回调的，注意替换的时候tencent保留，只替换后面的appid （不需要QQ或者微博可以不配置intent过滤，但是mobuishell这个activity必须要有）

	<QQ
        Id="7"
        SortId="7"
		AppId="1105417251"
		AppKey="B3BrUNp3GTMfsZcH"
        ShareByAppClient="true"
        Enable="true" />



	<activity
        android:name="com.mob.tools.MobUIShell"
        android:theme="@android:style/Theme.Translucent.NoTitleBar"
        android:configChanges="keyboardHidden|orientation|screenSize"
        android:screenOrientation="portrait"
       android:windowSoftInputMode="stateHidden|adjustResize" >
 	<!-- QQ和QQ空间分享 QQ登录的回调必须要配置的 -->
    <intent-filter>
           <data android:scheme="tencent1105417251" />
           <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.BROWSABLE" />
           <category android:name="android.intent.category.DEFAULT" />
    </intent-filter>

    <!-- 新浪微博客户端分享回调必须配置 -->
        <intent-filter>
                <action android:name="com.sina.weibo.sdk.action.ACTION_SDK_REQ_ACTIVITY" />
                <category android:name="android.intent.category.DEFAULT" />
        </intent-filter>
 </activity>





## 其他 ##
[集成指南](http://wiki.mob.com/Android_%E5%BF%AB%E9%80%9F%E9%9B%86%E6%88%90%E6%8C%87%E5%8D%97/)

[各个社交平台申请流程](http://bbs.mob.com/forum.php?mod=viewthread&tid=30&extra=page%3D1)

[腾讯开放平台](http://open.qq.com/)

[微信开发平台](https://open.weixin.qq.com/)