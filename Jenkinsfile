pipeline {
    agent {
        docker {
            image 'python:3.11-rc-bullseye'
            args '-p 4000:4000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
        stage('Test') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}