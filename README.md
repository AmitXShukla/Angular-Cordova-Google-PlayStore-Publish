# Angular-Cordova-Google-PlayStore-Publish
How to publish Angular 6 app to Google Play Store using Cordova

#### Objective:
This github repository is a documentation on how to publish an Angular 6.0/react JS or any HTML, JavaScript app to Google play store using Apache Cordova Framework.

https://cordova.apache.org/docs/en/latest/


#### Step
cordova -v  // check if 8.0.0 or latest cordova version is installed<br>
cordova create mnjic com.elishconsulting.mnjic Mnjic<br>
< cordova create appname com.domain.project appname >

cd mnjic

cordova platform add browser

cordova platform add android

cordova platform add ios

cordova plaform ls

install jdk and make sure JAVA_HOME is setup properly

install android studio and configure sdk tools

make sure android licenses are accepted

make sure android path/environment variables are setup properly

config.xml changes (make sure < android > setting are changed)  
- please see src directory for config.xml sample

apply following changes

favicon.ico
www -> replace directory, (back up index.html)

res -> icons// replace icons

#### test your app
cordova run browser

cordova run android

#### setup emulator for android
if emulator is slow for any reason, please skip this and generate android debug.apk file.
You can copy this apk file to any real android device and test your app.

generate keytools file

sign app - 

cordova run android --release -- --keystore=../my-release-key.keystore --storePassword=password --alias=alias_name --password=password.

review build.json

{
    "android": {
        "debug": {
            "keystore": "../android.keystore",
            "storePassword": "android",
            "alias": "mykey1",
            "password" : "password",
            "keystoreType": ""
        },
        "release": {
            "keystore": "../android.keystore",
            "storePassword": "",
            "alias": "mykey2",
            "password" : "password",
            "keystoreType": ""
        }
    }
}

#### cordova build
#### cordova build --release   // build with release flag will generate a final app file which can be submitted to Google Play Store.

release app

Prepare Google PlayStore ScreenShot

Publish to Google Play Store

***
In case, if you are releasing an updated release on your app.

Do NOT forget to change version code on next time your build your app (--release).
<widget id="com.elishconsulting.mnjic" version="1.0.0" xmlns="http://www.w3.org/ns/widgets" xmlns:cdv="http://cordova.apache.org/ns/1.0">
