# Android 工具类库 (Android Utils)

[![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=15)
[![Licence](https://img.shields.io/badge/licence-Apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)

本项目囊括了 Android 应用开发过程中常用的绝大部分工具类。这些工具类部分整理自网络，部分由开发者自行编写，旨在提高开发效率，减少重复造轮子。

## ✨ 核心特性

- **丰富全面**：包含文件、网络、图片、设备信息、加密解密等数十个常用工具类。
- **轻量易用**：无过多第三方依赖，即插即用。
- **兼容性好**：最低支持 API 15+。

## 📦 如何使用 (How to install)

> **注意**：由于 Bintray / JCenter 服务已下线，原有的 Maven 仓库引入方式已失效。建议通过 JitPack 引入，或直接将 `util` 模块作为本地 Library 导入到您的项目中。

### 方式一：本地模块导入 (推荐)
1. 下载或 Clone 本仓库代码。
2. 将 `util` 文件夹复制到您的项目中。
3. 在项目根目录的 `settings.gradle` 中包含该模块：
   ```groovy
   include ':util'
   ```
4. 在您 app 模块的 `build.gradle` 中添加依赖：
   ```groovy
   dependencies {
       implementation project(':util')
   }
   ```

### 方式二：通过 JitPack 引入
如果您已将此项目 Fork 并推送到 GitHub，可以通过 JitPack 引入：
```groovy
allprojects {
    repositories {
        // ...
        maven { url 'https://jitpack.io' }
    }
}
```
```groovy
dependencies {
    implementation 'com.github.您的用户名:android-utils:Tag版本号'
}
```

## 🛠 所有的工具类简介 (A - Z)

| 类 | 介绍 |
| ------ | ------------ |
| [AnimationUtils][1] | Animation 工具类 |
| [AppUtils][2] | APP 相关信息工具类 |
| [AssetDatabaseOpenHelper][3] | 读取 Asset 目录中数据库工具类 |
| [BitmapUtil][4] | Bitmap 工具类主要包括获取 Bitmap 和对 Bitmap 的操作 |
| [CipherUtils][5] | 加密与解密的工具类 (MD5, AES, DES, RSA 等) |
| [Colors][6] | 常用颜色色值工具类 |
| [CommonUtil][7] | 一些通用的方法 |
| [ChannelUtil][46] | 为打包而生的渠道工具类 |
| [DataCleanManager][8] | 应用数据清除类（内/外缓存，数据库，SharedPreference，files 及自定义目录）|
| [DatabaseExportUtils][9] | 导出应用数据库工具类 |
| [DateUtils][10] | 日期时间格式化与解析工具类 |
| [DeviceStatusUtils][11] | 手机状态工具类（网络、蓝牙、屏幕亮度、飞行模式、音量等）|
| [DeviceUtils][51] | 获取设备唯一标志 |
| [DisplayUtils][13] | 系统显示相关工具类 (dp/px 转换等) |
| [DoubleKeyValueMap][14] | 双键值对数据结构 |
| [DownloadManagerPro][15] | 下载管理工具类 |
| [FileUtils][16] | 文件操作工具类（读写、复制、删除等）|
| [HanziToPinyin][17] | 汉字转拼音工具类 |
| [ImsiUtil][18] | IMSI 获取工具类 |
| [JSONUtils][48] | Json 解析与封装工具类 |
| [LocationUtils][19] | 经纬度与地址信息互转工具 |
| [LogUtils][20] | Log 日志打印工具类，支持统一控制日志级别 |
| [NetUtil][21] | 网络状态检测与类型判断工具类 |
| [PackageUtils][22] | 应用安装下载相关工具类 (静默安装等) |
| [PhoneUtil][23] | 手机组件调用工具类（拨打电话、发短信等）|
| [PollingUtils][24] | 轮询服务工具类（开启/停止轮询服务）|
| [PreferencesCookieStore][25] | Cookie 存储工具类 |
| [RUtils][26] | 反射获取 R 资源 ID 工具类 |
| [RandomUtils][27] | 随机数生成工具类 |
| [RegUtils][28] | 数据校验（正则表达式）工具类（手机号、邮箱、身份证等）|
| [ResourceUtils][29] | 文件资源读取工具类 (assets/raw) |
| [SDCardUtils][30] | SD 卡状态与路径操作工具类 |
| [SettingUtils][31] | 应用系统设置工具类 |
| [SharesUtils][50] | 调用手机自带的分享（字符串或图片）|
| [ShellUtils][32] | Shell 命令行执行工具类（支持 root）|
| [ShortCutUtils][33] | 桌面快捷方式工具类 |
| [Singleton][34] | 单例模式抽象基类 |
| [StringUtils][35] | 字符串操作辅助包 |
| [ToastsUtils][49] | Toast 统一管理与弹框工具 |
| [ViewAnimationUtils][36] | 视图动画工具箱 |
| [ViewFinder][45] | `findViewById` 替代工具类 |
| [ViewUtils][37] | View 测量与操作相关工具类 |
| [WindowUtils][38] | 窗口与屏幕工具类 |
| [BaseApplication][39] | 基础 Application（内置全局异常捕获处理）|
| [BaseCrashHandler][40] | 统一捕获异常并保存到文件，下次打开时可上传 |
| [RebootThreadExceptionHandler][41]| 重启线程异常处理器，发生未知异常时自动重启应用 |
| [StartAppReceiver][42] | 重启应用广播接收器 |

## 🔒 需要的权限 (Permissions)

在您的 `AndroidManifest.xml` 中按需添加以下权限：

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.BLUETOOTH" />
<!-- 获取 UUID (设备状态) 用到 -->
<uses-permission android:name="android.permission.READ_PHONE_STATE" />
```

## ⚙️ 配置 (Configuration)

### 全局崩溃捕获 (可选)
如果需要全局的异常捕获与应用重启功能，可在 `AndroidManifest.xml` 中配置内置的 Application：
```xml
<application
    android:name="com.ihongqiqu.app.BaseApplication" 
    ...>
</application>
```

### 日志输出控制
发布正式版本时，若想关闭或过滤 Log 日志，只需在代码初始化处设置：
```java
LogUtils.DEBUG_LEVEL = Log.ASSERT;
```

## 🛡 混淆 (Proguard)

如果您的项目启用了代码混淆，请在 Proguard 规则文件 (`proguard-rules.pro` 或 `proguard.cfg`) 中添加如下代码以防止工具类被错误混淆：

```proguard
-keep class com.ihongqiqu.** { *; }
-keepclassmembers class com.ihongqiqu.** { *; }
-dontwarn com.ihongqiqu.**
```

## 📖 Framework 内置工具类参考

在造轮子之前，也可以参考 AOSP 源码中自带的一些常用 Util 类（部分列出）：

```java
// 系统
android.database.DatabaseUtils
android.transition.TransitionUtils
android.view.animation.AnimationUtils
android.view.ViewAnimationUtils
android.webkit.URLUtil
android.bluetooth.le.BluetoothLeUtils
android.gesture.GestureUtils
android.text.TextUtils
android.text.format.DateUtils
android.os.FileUtils
android.net.NetworkUtils
android.util.MathUtils
android.util.TimeUtils
android.util.ExceptionUtils
android.telephony.PhoneNumberUtils
// ...
```

## 👨‍💻 开发者 (Developer)

* [Zhenguo Jin][44] - <jinzhenguo1990@gmail.com>

## 📄 License

    Copyright 2014-2017 Zhenguo Jin

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

<!-- Links -->
[1]: util/src/main/java/com/ihongqiqu/util/AnimationUtils.java
[2]: util/src/main/java/com/ihongqiqu/util/AppUtils.java
[3]: util/src/main/java/com/ihongqiqu/util/AssetDatabaseOpenHelper.java
[4]: util/src/main/java/com/ihongqiqu/util/BitmapUtil.java
[5]: util/src/main/java/com/ihongqiqu/util/CipherUtils.java
[6]: util/src/main/java/com/ihongqiqu/util/Colors.java
[7]: util/src/main/java/com/ihongqiqu/util/CommonUtil.java
[8]: util/src/main/java/com/ihongqiqu/util/DataCleanManager.java
[9]: util/src/main/java/com/ihongqiqu/util/DatabaseExportUtils.java
[10]: util/src/main/java/com/ihongqiqu/util/DateUtils.java
[11]: util/src/main/java/com/ihongqiqu/util/DeviceStatusUtils.java
[13]: util/src/main/java/com/ihongqiqu/util/DisplayUtils.java
[14]: util/src/main/java/com/ihongqiqu/util/DoubleKeyValueMap.java
[15]: util/src/main/java/com/ihongqiqu/util/DownloadManagerPro.java
[16]: util/src/main/java/com/ihongqiqu/util/FileUtils.java
[17]: util/src/main/java/com/ihongqiqu/util/HanziToPinyin.java
[18]: util/src/main/java/com/ihongqiqu/util/ImsiUtil.java
[19]: util/src/main/java/com/ihongqiqu/util/LocationUtils.java
[20]: util/src/main/java/com/ihongqiqu/util/LogUtils.java
[21]: util/src/main/java/com/ihongqiqu/util/NetUtil.java
[22]: util/src/main/java/com/ihongqiqu/util/PackageUtils.java
[23]: util/src/main/java/com/ihongqiqu/util/PhoneUtil.java
[24]: util/src/main/java/com/ihongqiqu/util/PollingUtils.java
[25]: util/src/main/java/com/ihongqiqu/util/PreferencesCookieStore.java
[26]: util/src/main/java/com/ihongqiqu/util/RUtils.java
[27]: util/src/main/java/com/ihongqiqu/util/RandomUtils.java
[28]: util/src/main/java/com/ihongqiqu/util/RegUtils.java
[29]: util/src/main/java/com/ihongqiqu/util/ResourceUtils.java
[30]: util/src/main/java/com/ihongqiqu/util/SDCardUtils.java
[31]: util/src/main/java/com/ihongqiqu/util/SettingUtils.java
[32]: util/src/main/java/com/ihongqiqu/util/ShellUtils.java
[33]: util/src/main/java/com/ihongqiqu/util/ShortCutUtils.java
[34]: util/src/main/java/com/ihongqiqu/util/Singleton.java
[35]: util/src/main/java/com/ihongqiqu/util/StringUtils.java
[36]: util/src/main/java/com/ihongqiqu/util/ViewAnimationUtils.java
[37]: util/src/main/java/com/ihongqiqu/util/ViewUtils.java
[38]: util/src/main/java/com/ihongqiqu/util/WindowUtils.java
[39]: app/src/main/java/com/ihongqiqu/app/BaseApplication.java
[40]: app/src/main/java/com/ihongqiqu/app/BaseCrashHandler.java
[41]: app/src/main/java/com/ihongqiqu/app/RebootThreadExceptionHandler.java
[42]: app/src/main/java/com/ihongqiqu/app/StartAppReceiver.java
[44]: http://ihongqiqu.com
[45]: util/src/main/java/com/ihongqiqu/util/ViewFinder.java
[46]: util/src/main/java/com/ihongqiqu/util/ChannelUtil.java
[48]: util/src/main/java/com/ihongqiqu/util/JSONUtils.java
[49]: util/src/main/java/com/ihongqiqu/util/ToastsUtils.java
[50]: util/src/main/java/com/ihongqiqu/util/SharesUtils.java
[51]: util/src/main/java/com/ihongqiqu/util/DeviceUtils.java