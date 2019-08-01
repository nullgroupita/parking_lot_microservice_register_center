pipeline {
  agent any
  stages {
    stage('Gradle build') {
      steps {
        sh '''chmod 700 ./gradlew
./gradlew clean build'''
      }
    }
    stage('Deploy To Staging') {
      steps {
        sh 'cp /root/.jenkins/workspace/parking_lot_microservice_register_center_dev/build/libs/parking_lot_microservice_register_center-0.0.1-SNAPSHOT.jar /workspace/BackEnd/center.jar'
      }
    }
  }
}