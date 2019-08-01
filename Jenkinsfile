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
        sh '''cp /root/.jenkins/workspace/roservice_register_center_master/build/libs/eureka-0.0.1-SNAPSHOT.jar /workspace/BackEnd/eureka.jar
cd /workspace/BackEnd
p=`jps -l | grep eureka | grep -P \'\\d+\' -o`
sudo kill -9 $p
JENKINS_NODE_COOKIE=dontKillMe
nohup java -jar eureka.jar >run.txt 2>&1 &'''
      }
    }
  }
}