pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                sh 'git clone https://192.168.65.129/root/todo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}