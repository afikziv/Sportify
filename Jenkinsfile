pipeline {
  agent {
    docker {
      image 'windsekirun/jenkins-android-docker:1.1.1'
    }
  }
  options {
    skipStagesAfterUnstable()
  }
  stages {
    stage ('Prepare'){
      steps {
        sh 'chmod +x ./gradlew'
      }
    }
    stage('Compile') {
      steps {
        sh './gradlew compileDebugSources'
      }
    }
    stage('Build APK') {
      steps {
        sh './gradlew assembleDebug'
      }
    }
  }
}
