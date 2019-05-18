pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'echo Beer'
            }
        }
        stage('Test') { 
            
            steps {
                wrap([$class: 'BuildUser']) {
 // https://wiki.jenkins-ci.org/display/JENKINS/Build+User+Vars+Plugin variables available inside this block

                   sh 'echo ${BUILD_USER}'
                }
                sh 'echo mohamed'
                sh 'echo $BUILD_USER'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo Asai' 
            }
        }
    }
}
