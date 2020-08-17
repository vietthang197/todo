pipeline {
    agent any
    stages {
        stage('Clone') {
                steps {
                    sh 'cd todo'
                    sh 'git pull origin master'
                }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}