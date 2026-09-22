pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t mi-app-web:${BUILD_NUMBER} .'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Simulando pruebas unitarias..."'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker rm -f app-web || true'
                sh 'docker run -d -p 8080:3000 --name app-web mi-app-web:${BUILD_NUMBER}'
            }
        }
    }
}
