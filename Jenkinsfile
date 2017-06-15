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
}
