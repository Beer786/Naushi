pipeline {
    agent any 
    environment {
    BUILD_USER = "${sh(returnStdout: true, script: 'curl -u admins:11a8ebaa21bd67c9e29fee6af4cda44e77 --silent ${BUILD_URL}api/json | tr "{}" "\n" | grep "Started by" | awk -F, \'{print $NF}\'| awk -F: \'{print $NF}\'| sed \'s/\"//g\'')}"
   // BUILD_USER = "${sh(returnStdout: true, script: 'curl -u admins:11a8ebaa21bd67c9e29fee6af4cda44e77 --silent ${BUILD_URL}api/json | jq -r .actions[].causes[0].userName| grep -v null)}"

    }
    stages {
        stage('Build') { 
            steps {
                sh 'echo Beer'
                sh 'echo BEERUSER ${BUILD_USER}'
            }
        }
        stage('Test') { 
            
            steps {
                wrap([$class: 'BuildUser']) {
 // https://wiki.jenkins-ci.org/display/JENKINS/Build+User+Vars+Plugin variables available inside this block
               script {
                def user = '${BUILD_USER}'
               }
                sh 'echo BEER ${user}'
                   sh 'echo ${BUILD_USER}'
                
                sh 'echo mohamed'
                sh 'echo User Name: ${BUILD_USER}'
                sh 'echo First Name: ${BUILD_USER_FIRST_NAME}'
                sh 'echo User mail: ${BUILD_USER_EMAIL}'
              
                }
            }
        }
    }
      
    post {
        success {
            mail to : "mohamed.beer@gmail.com",
            subject: "test",
            body : "User is ${BUILD_USER}"
                
            }
     
        }
    

}
