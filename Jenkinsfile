pipeline {
    agent any
    stages {
        stage('Pull') {
            def exists = fileExists('todo')
            if (exists) {
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