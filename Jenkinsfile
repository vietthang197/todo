pipeline {
    agent any
    stages {
        stage('Build') {
            if (fileExists('todo')) {
                steps {
                    sh 'git clone https://192.168.65.129/root/todo.git'
                }
            } else {
                steps {
                    sh 'cd todo'
                    sh 'git pull origin master'
                }
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}