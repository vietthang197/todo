pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                sh 'git clone https://192.168.65.129/root/todo.git'
            }
        }
        stage('Build') {
            script {
                def pom = readMavenPom file: 'pom.xml'
            }
            steps {
                sh 'mvn clean package'
                sh 'docker push levietthang1997/${pom.projectName}:${pom.projectVersion}'
            }
        }
    }
}