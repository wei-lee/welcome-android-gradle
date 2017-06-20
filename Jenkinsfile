node("android"){
  stage("checkout"){
    checkout scm
  }
     
  stage("build"){
    sh 'chmod +x ./gradlew'
    sh './gradlew clean assembleRelease' // builds app/build/outputs/app-release-unsigned.apk file
  }
  
  stage("sign"){
    signAndroidApks (
        keyStoreId: "${params.BUILD_CREDENTIAL_ID}",
        keyAlias: "${params.BUILD_CREDENTIAL_ALIAS}",
        apksToSign: "**/*-unsigned.apk",
        // uncomment the following line to output the signed APK to a separate directory as described above
        // signedApkMapping: [ $class: UnsignedApkBuilderDirMapping ],
        // uncomment the following line to output the signed APK as a sibling of the unsigned APK, as described above, or just omit signedApkMapping
        // you can override these within the script if necessary
        // androidHome: '/usr/local/Cellar/android-sdk',
        zipalignPath: '/opt/android-sdk-linux/build-tools/25.0.3/zipalign'
    )
  }

  stage('Archive'){
    archiveArtifacts artifacts: 'app/build/outputs/apk/app-release.apk', excludes: 'app/build/outputs/apk/*-unaligned.apk'
	  println('Done!')
  }
}
