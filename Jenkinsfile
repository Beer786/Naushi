pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'echo Beer'
            }
        }
        stage('Test') { 
            wrappers {
            buildUserVars()
            }
            steps {
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
