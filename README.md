# Angular-Cordova-Google-PlayStore-Publish
How to publish Angular 6 app to Google Play Store using Cordova

#### Objective:
This github repository is a documentation on how to publish an Angular 6.0/react JS or any HTML, JavaScript app to Google play store using Apache Cordova Framework.

#### Step
cordova -v  // check if 8.0.0 or latest cordova version is installed<br>
cordova create mnjic com.elishconsulting.mnjic Mnjic<br>
< cordova create appname com.domain.project appname >

cd mnjic

platform add browser

platform add android

platform add ios

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

setup emulator for android

generate keytools file

review build.json

sign app - 

release app

Prepare Google PlayStore ScreenShot

Publish to Google Play Store
