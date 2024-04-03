pipeline {
    agent any

      stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'cd webapp && npm install && npm run build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'cd webapp && sudo docker container run --rm -e SONAR_HOST_URL="http:/54.200.166.175:9000" -e SONAR_LOGIN="sqp_f417783426ea42f56130ee850f69ca9f755e5d4b" -v ".:/usr/src" sonarsource/sonar-scanner-cli -Dsonar.projectKey=lms'
            }
        }
      }
}              
