pipeline {
    agent none
    stages {

        stage('getEnvInfo'){
          steps {
              sh “whoami”
            }
        }


        stage('Build') {
            agent {
                docker {
                    image 'python:2-alpine'
                }
            }
            steps {
                sh “whoami”
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
