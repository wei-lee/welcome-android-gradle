node("android"){
  stage("checkout"){
    checkout scm
  }
     
  stage("build"){
    sh 'curl http://google.com'
    sh 'echo $ANDROID_HOME'
    sh 'which zipalign'
    sh './gradlew clean assembleRelease' // builds app/build/outputs/app-release-unsigned.apk file
  }
  
  stage("sign"){
    signAndroidApks (
        keyStoreId: "test-credentials",
        keyAlias: "",
        apksToSign: "**/*-unsigned.apk",
        // uncomment the following line to output the signed APK to a separate directory as described above
        // signedApkMapping: [ $class: UnsignedApkBuilderDirMapping ],
        // uncomment the following line to output the signed APK as a sibling of the unsigned APK, as described above, or just omit signedApkMapping
        // you can override these within the script if necessary
        // androidHome: '/usr/local/Cellar/android-sdk',
        // zipalignPath: '/usr/local/Cellar/android-sdk/24.4.1_1/build-tools/25.0.2'
    )
  }
}
