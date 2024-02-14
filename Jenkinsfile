/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent {
        node {
            label 'docker-agent-alpine'
            }
      }
    triggers {
        pollSCM 'H/2 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '''
                cd myapp
                pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name Claude
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
