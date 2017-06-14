node("android"){
  stage("checkout"){
    checkout scm
  }
     
  stage("build"){
    sh 'pwd'
    sh 'ls -laht'
    sh 'curl http://google.com'
    sh './gradlew clean assembleDebug'
  }
}
