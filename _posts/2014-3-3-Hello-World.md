---
layout: post
title: 'Hello,'
published: true
---

## Generating an APK for cordova Project
   Step 1  
   
   generate a release build from cordovan 
   cd to your project directory eg. E:\Africa\mobile>
   run: cordova build --release android
   This will generate an unsigned apk in:platforms/android/ant-build/Example-release-unsigned.apk
   
   Step 2  
   Generate a keystore  
   Syntax    
   edit everything enclosed in <>  
   keytool -genkey -v -keystore <keystoreName>.keystore -alias <Keystore AliasName> -keyalg <Key algorithm> -keysize     <Key size> -validity <Key Validity in Days>  
  eg.  
  keytool -genkey -v -keystore key-mobileappHCH.keystore -alias alias_mobileappHCH -keyalg RSA -keysize 2048 
  -validity 10000

   