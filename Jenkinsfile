pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python3.12.0b4-alpine3.18'
                }
            }
            steps {
                sh 'python3.12 -m py_compile sources/prog.py sources/calc.py'
                stash(name: 'compiled-results', includes: 'sources/*.py*')
            }
        }
    }
}
