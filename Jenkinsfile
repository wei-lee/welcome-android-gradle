node("android"){
  stage("checkout){
    checkout scm
  }
     
  stage("build"){
    sh 'pwd'
    sh 'ls -laht'
    sh './gradlew clean assembleDebug'
  }
}
