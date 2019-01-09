pipeline {
    agent any
    stages {

          stage('getEnvInfo'){
              steps {
                wrap([$class: 'BuildUser']) {
                sh 'echo "${BUILD_USER}"'
              }
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
