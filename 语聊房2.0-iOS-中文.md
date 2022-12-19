# 文档框架-中文-iOS

# 1.项目介绍

## 1.1 概述

项目名称：声动语聊

声动语聊项目是声网语聊房场景的开源代码，开发者可以获取并添加到您的APP工程里，本源码会伴随声动语聊Demo同步更新，为了获取更多新的功能和更佳的音效，强烈推荐您下载最新代码集成。

## 1.2 功能介绍

声动语聊目前已涵盖以下功能，您可以参考注释按需从代码中调用：

* 房间管理：房间列表管理，创建房间
    *  功能代码路径：AgoraScene_iOS/AgoraScene_iOS/Business/RoomService/
* 席位管理：踢人，麦位静音，麦位锁定
    * 麦位管理相关功能主要依托于组件MicPosView，拖拽到项目中即可使用
    * AgoraChatRoomNormalRtcView：基础麦位组件，支持麦位的上下麦，换麦，静音/解除静音，锁麦/解锁，麦位的单个刷新，音量更新等麦位功能。
    * 麦位相关操作逻辑请参考VoiceRoomViewController.swift文件
* 互动：弹幕，打赏
    * IM相关的弹幕和打赏请参考VoiceRoomViewController+IM.swift文件
    * 当前版本使用的环信IM，用户可以自主选择集成的IM
* 音效：声网最佳音效，AI降噪
    * 音效方法参考：VoiceRoomViewController+ChatBar.swift文件的 func showEQView()
    * 该方法支持对音效功能的统一处理
# 2.使用场景

声网声动语聊源码，最终目的是方便开发者快速按需集成，减少开发者搭建语聊房的工作量。在现有源码的基础上，您可以按需自由定制，包括UI/UE，前端逻辑，权限体系等

# 3.集成步骤

```plain
在您的podfile文件里面，需要添加以下几个第三方库
# 布局
  pod 'SnapKit'
# 刷新
  pod 'MJRefresh', '~> 3.2.0'
# toast
  pod 'MBProgressHUD', '~> 1.1.0'
# 加载图片
  pod 'SDWebImage', '~> 5.0.3'
# 键盘
  pod 'IQKeyboardManager'
# RTC Agora音视频
  pod 'AgoraRtcEngine_Special_iOS', '4.0.0.9'
# 矢量动画
pod 'SVGAPlayer'
# 字典转模型
pod 'KakaJSON'
# AgoraChat IM
pod 'Agora_Chat_iOS','1.0.8'
然后pod install成功之后，打开项目即可开始您的体验。

在集成的同时，需要去声网合环信的官网注册好对应的账号，同时开通对应的权限从而快速开始你的体验
在项目的keycenter.swift文件中。需要填写对应的账号和token
AppId：声网appid
Certificate：声网Certificate
Token：默认为nil，这个会在服务端生成，可以忽略

HostUrl：这个是服务端Url，由服务端确认

IMAppKey：环信appkey
IMClientId：环信IMClientId
IMClientSecret：环信IMClientSecret

onlineBaseServerUrl：获取IM，RTC的信息的url前缀，这个服务端来指定

配置好这些参数之后。就可以快速开始体验了♥️

```
# 4.FAQ

* 如何获取声网和环信APPID：
    * 声网APPID申请：[https://www.agora.io/cn/](https://www.agora.io/cn/)
    * 环信APPID申请：[https://www.easemob.com/](https://www.easemob.com/)
* 语聊房中的弹幕组件使用的是哪家？是否可以自己选择供应商？
声动语聊源码使用的是环信AgoraChat的IM和信令服务，您也可以使用自己的服务

* 集成遇到困难，该如何联系声网获取协助
方案1：如果您已经在使用声网服务或者在对接中，可以直接联系对接的销售或服务；

方案2：发送邮件给support@agora.io咨询

# 文档框架-中文-Android

**1.项目介绍**

## 1.1 概述

项目名称：声动语聊

声动语聊项目是声网语聊房场景的开源代码，开发者可以获取并添加到您的APP工程里，本源码会伴随声动语聊Demo同步更新，为了获取更多新的功能和更佳的音效，强烈推荐您下载最新代码集成。

## 1.2 功能介绍

声动语聊目前已涵盖以下功能，您可以参考注释按需从代码中调用：

* 房间管理：房间列表管理，创建房间
    *  协议路径：[https://github.com/](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[Agora](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[IO-Use](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[c](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[ase/agora-](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[en](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[t-scenarios/blob/feat/sc](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[e](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[ne/voicechat](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[_](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[andro](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[i](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[d](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[/A](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[ndroid/scenes/voice/voice/src/main/java/io/a](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[gora](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[/s](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[cene](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[/vo](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[i](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[ce](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[/s](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[erv](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[i](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[c](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[e/](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[V](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[o](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[iceSyncManager](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[Service](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)[Imp.kt](https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/service/VoiceSyncManagerServiceImp.kt)
* 席位管理：踢人，麦位静音，麦位锁定
    * 麦位管理相关功能主要依托于组件Room2DMicLayout
    * roomObservableDelegate：管理房间头部以及麦位置数据变化代理，支持麦位的上下麦，换麦，静音/解除静音，锁麦/解锁，麦位的单个刷新，音量更新等麦位功能。
    * 麦位相关操作逻辑请参考VoiceSyncManagerServiceImp 协议文件
* 互动：弹幕，打赏
    * IM相关的弹幕和打赏请参考ChatroomGiftView 和 ChatroomMessagesView文件
    * 当前使用的环信IM SDK 1.0.8版本，用户可以自主选择集成的IM
* 音效：声网最佳音效，AI降噪
    * 音效、AI降噪参考：AgoraRtcEngineController
    * 该l类支持对音效功能的统一处理
# 2.使用场景

声网声动语聊源码，最终目的是方便开发者快速按需集成，减少开发者搭建语聊房的工作量。在现有源码的基础上，您可以按需自由定制，包括UI/UE，前端逻辑，权限体系等

# 3.集成步骤

```plain
准备引入资源:
在根目录build.gradle中 配置 mavenCentral()仓库
在app目录下build.gradle中添加:
IM SDK: implementation 'io.agora.rtc:chat-sdk:1.0.8' 
RTC SDK: implementation 'io.agora.rtc:agora-special-full:4.0.1.2'
权限获取：implementation 'pub.devrel:easypermissions:3.0.0'
syncManager implementation 'com.github.AgoraIO-Community:SyncManager-Android:2.1.2'
glide implementation 'com.github.bumptech.glide:glide:$glide_version'
lifecycle implementation 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.4.1'
svga_player implementation 'com.github.yyued:SVGAPlayer-Android:2.6.1'
gson implementation 'com.google.code.gson:gson:2.9.0'
此项目需要appserver配合 在gradle.properties文件中配置SERVER_HOST、AGORA_APP_ID（从声网console获取）、AGORA_APP_CERTIFICATE	（从声网console获取）
重要类介绍:
AgoraRtc管理类：[AgoraRtcEngineController]: https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/rtckit/AgoraRtcEngineController.kt
IM配置管理类(主要包括初始化IM SDK 设置回调监听)：[ChatroomConfigManager]: https://github.com/AgoraIO-Usecase/agora-ent-scenarios/tree/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/imkit/manager/ChatroomConfigManager.java
自定义消息帮助类（主要用来发送自定义消息 解析自定义消息需要的属性)[CustomMsgHelper]: https://github.com/AgoraIO-Usecase/agora-ent-scenarios/blob/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/imkit/custorm/CustomMsgHelper.java
IM管理类（包含加入房间、登录、退出登录等）[ChatroomIMManager]: https://github.com/AgoraIO-Usecase/agora-ent-scenarios/tree/feat/scene/voicechat_android/Android/scenes/voice/voice/src/main/java/io/agora/scene/voice/imkit/manager/ChatroomIMManager.java
整体流程:
1、初始化环信IM SDK ChatroomConfigManager为项目中封装的IM 配置管理类 这里配置从环信获取的appkey等基本信息 之后登录环信
		ChatroomConfigManager.getInstance().initRoomConfig()
		ChatroomIMManager.getInstance().login()
2、创建房间、获取房间列表需要由appserver配合实现
3、加入房间时 获取rtc所需权限 成功获取权限后初始化rtc sdk并加入channel
		AgoraRtcEngineController.get().joinChannel()//加入rtc channel
		ChatroomIMManager.getInstance().joinChatRoom()//加入房间
		权限获取可以参考 onPermissionGrant 方法 初始化rtc可以参考VoiceRoomLivingViewModel中initSdkJoin()方法
4、发送弹幕消息或者打赏礼物
		ChatroomIMManager.getInstance().sendTxtMsg()//发送弹幕消息
		CustomMsgHelper.getInstance().sendGiftMsg()//发送礼物消息
5、退出房间 可以参考 ChatroomLiveActivity类中的finish()方法
		ChatroomIMManager.getInstance().logout()//退出登录
		ChatroomIMManager.getInstance().leaveChatRoom()//成员直接退出房间
		ChatroomIMManager.getInstance().asyncDestroyChatRoom//owner退出可以销毁房间
```
# 4.FAQ

* 如何获取声网和环信APPID：
    * 声网APPID申请：[https://www.agora.io/cn/](https://www.agora.io/cn/)
    * 环信APPKEY申请：[https://www.easemob.com/](https://www.easemob.com/)
* 语聊房中的弹幕组件使用的是哪家？是否可以自己选择供应商？
声动语聊源码使用的是环信AgoraChat的IM和信令服务，您也可以使用自己的服务

* 集成遇到困难，该如何联系声网获取协助
方案1：如果您已经在使用声网服务或者在对接中，可以直接联系对接的销售或服务；

方案2：发送邮件给support@agora.io咨询

# 文档框架-英文

2.1 Project introduction

2.2 Use Scenarios

2.3 Integration steps

2.4 FAQ

