1. npm install cordova
2. cordova 可以将 web 网站转为 apk 或者 ios 原生的应用
3. 编译 apk 和 ios 时电脑需要对应的环境。这个 cordova 官网有提供 。以下为 mac 下生成 apk

   1. Android 直接在系统先安装 Android Studio 然后直接选择 SDK 的版本即可，没必要单独下载，防止有些依赖忽略掉
   2. 安装 gradle 可以通过 brew install gradle 即可
   3. 然后就可以用 cordova 生成 apk 文件了
   4. 最后，电脑也要安装 java 的 SDK

4. 以下为 cordova app 需要的包：  
    Java JDK: installed 1.8.0
   Android SDK: installed true
   Android target: installed android-28
   Gradle: installed /usr/local/Cellar/gradle/5.6.4/bin/gradle

5. IOS 类似 有些苹果的包是需要单独安装的。

6. [Demo 地址](https://github.com/ZhixianKwok/vue-cordova.git)
