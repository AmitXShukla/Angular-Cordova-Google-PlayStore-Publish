# Angular-Cordova-Google-PlayStore-Publish
How to publish Angular 6 app to Google Play Store using Cordova

#### Objective:
This github repository is a documentation on how to publish an Angular 6.0/react JS or any HTML, JavaScript app to Google play store using Apache Cordova Framework.

https://cordova.apache.org/docs/en/latest/


#### Development tasks
Before you start, if you don't already have, please download and Install android studio and configure sdk tools from
https://developer.android.com/studio/

make sure android licenses are accepted

make sure android path/environment variables are setup properly

** for iOS development, you will need a mac machine with latest XCODE installed.

**** Let's get started

cordova -v  // check if 8.0.0 or latest cordova version is installed<br>
cordova create mnjic com.elishconsulting.mnjic Mnjic<br>  
create a new cordova app <br>
< cordova create appname com.domain.project appname >

cd mnjic // once app is created, browse into new app folder

cordova platform add browser // add platform browser

cordova platform add android  // add platform android

cordova platform add ios // add platform ios

cordova plaform ls // list all platforms

install jdk and make sure JAVA_HOME is setup properly

#### Run these commands on your MACOS terminal window
#### On windows machine, please make sure SYSTEM > Env Variables JAVA_HOME and ANDROID_HOME are set properly
which java

java -version

export JAVA_HOME=/Library/Java/Home

echo $JAVA_HOME

echo $ANDROID_HOME

#### if ANDROID_HOME is not setup correctly,
export ANDROID_HOME=~/Library/Android/sdk

export PATH=${PATH}:~/Library/Android/sdk/platform-tools:~/Library/Android/sdk/tools

echo $ANDROID_HOME

echo $PATH

#### cordova requirements // check if cordova app is properly installed
in some case, if may ask you to update Android SDK through Android Studio.

and install gradle.

$ java -version<br>
java version "1.8.0_121"

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install gradle

#### App Setting changes
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
