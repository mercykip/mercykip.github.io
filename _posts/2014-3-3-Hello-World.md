---
layout: post
title: 'Hello,'
published: true
---

## Generating an APK for cordova Project
   Step 1 : generate a release build from cordova project  
   cd to your project directory  
   eg. E:\Africa\mobile>  
   run: _cordova build --release android_  
   This will generate an unsigned apk in:platforms/android/ant-build/Example-release-unsigned.apk
   
   Step 2 : Generate a keystore   
   Syntax    
   edit everything enclosed in <> 
   keytool -genkey -v -keystore <**_keystoreName_**>.keystore -alias <**Keystore AliasName**__> -keyalg <**Key algorithm**__> -keysize     <**Key size**__> -validity <**Key Validity in Days**__>   
  eg.  
  keytool -genkey -v -keystore key-mobileappHCH.keystore -alias alias_mobileappHCH -keyalg RSA -keysize 2048 
  -validity 10000
  
  Step 3 : Sign the unsigned APK  
  cd your release folder eg.  
  E:\Africa\mobile>cd E:\Africa\mobile\platforms\android\app\build\outputs\apk\release  
  run:  
  jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore key-mobileappHCH.keystore app-release-unsigned.apk alias_mobileappHCH  
  Syntax  
  jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore <**keystorename**__> <**Unsigned APK file**__> <**Keystore Alias name**__>  
  
  Step 4 : Zip the signed apk
  
  find the android sdk path eg  
  C:\Android\build-tools\29.0.2\  
  cd your release forlder  
  E:\Africa\mobile\platforms\android\app\build\outputs\apk\release  
  run : 
  E:\Africa\mobile\platforms\android\app\build\outputs\apk\release>C:\Android\build-tools\29.0.2\zipalign -v 4 app-release-unsigned.apk hch.apk


  
   

