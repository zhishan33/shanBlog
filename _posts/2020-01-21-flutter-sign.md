---
layout: default
title: flutter sign notes
date: 2020-01-21 +0800
categories: flutter
tags: [flutter, andriod, notes]
---

## flutter 签名 notes

### Flutter项目跟目录命令行输入：
> keytool -genkey -v -keystore D:/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key

### 输入查看签名详情 包括SHA1等信息
> keytool -list -v -keystore D:\key.jks
> keytool -list -v -keystore F:\APP\sign.jks -alias sign -storepass 123456 -keypass 123456

### 配置android\app\build.gradle 在buildTypes上面添加

```gradel
// add
def keystorePropertiesFile = rootProject.file("key.properties")
def keystoreProperties = new Properties()
keystoreProperties.load(new FileInputStream(keystorePropertiesFile))

android {
    compileSdkVersion 28

    sourceSets {
        main.java.srcDirs += 'src/main/kotlin'
    }

    lintOptions {
        disable 'InvalidPackage'
    }

    defaultConfig {
        // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
        applicationId "net.zikaoshu.app"
        minSdkVersion 16
        targetSdkVersion 28
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }
//add
    signingConfigs {
        debug {
            storeFile file("../my-release-key.jks")
            storePassword "123456"
            keyAlias "key"
            keyPassword "123456"
        }
        release {
            storeFile file("../my-release-key.jks")
//            storePassword "123456"
//            keyAlias "key"
//            keyPassword "123456"
            keyAlias keystoreProperties['keyAlias']
            keyPassword keystoreProperties['keyPassword']
//            storeFile file(keystoreProperties['storeFile'])
            storePassword keystoreProperties['storePassword']
        }
    }

    buildTypes {
			//modify
        release {
            // TODO: Add your own signing config for the release build.
            // Signing with the debug keys for now, so `flutter run --release` works.
            signingConfig signingConfigs.release
        }
        debug {
            signingConfig signingConfigs.debug

        }
    }
}


```


### 打包APK
>flutter build apk
>flutter build apk --target-platform android-arm,android-arm64 --split-per-abi

### 安装APK
> flutter install

### 微信公众平台申请移动应用的时候，会要求你填写应用签名，这个签名，其实就是这个MD5值，去掉中间的冒号，同时变成小写的值：77fc1ddf2ba022edbd93a864ce42ceef


## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)
* [AndroidStudio中Flutter打包APK](https://www.cnblogs.com/niceyoo/p/11046253.html)
* [FLUTTER打release包，签名](https://www.jianshu.com/p/825e305de61d)

> {{page.date | date: '%Y, %b %d' }}
