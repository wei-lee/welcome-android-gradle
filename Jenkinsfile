node("android"){
  stage("checkout"){
    checkout scm
  }
     
  stage("build"){
    sh 'pwd'
    sh 'ls -laht'
    sh 'curl http://google.com'
    sh 'wget https://s3.eu-central-1.amazonaws.com/aliok-tmp/app-debug.apk'
    //sh './gradlew clean assembleDebug'
  }
  
  stage("sign"){
    signAndroidApks (
        keyStoreId: "myApp.signerKeyStore",
        keyAlias: "myTeam",
        apksToSign: "**/*.apk"
        // uncomment the following line to output the signed APK to a separate directory as described above
        // signedApkMapping: [ $class: UnsignedApkBuilderDirMapping ]
        // uncomment the following line to output the signed APK as a sibling of the unsigned APK, as described above, or just omit signedApkMapping
        // you can override these within the script if necessary
        // androidHome: env.ANDROID_HOME
        // zipalignPath: env.ANDROID_ZIPALIGN
    )
  }
}
