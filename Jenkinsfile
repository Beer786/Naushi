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
                wrappers {
                 buildUserVars()
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
