pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git branch: "master", url: 'https://10.252.10.175/thanglv/todo.git'
            }
        }
        stage('Build') {
            steps {
                script {
                   pom = readMavenPom file: "pom.xml"
                }
                sh 'mvn clean package dockerfile:build'
                sh 'docker push levietthang1997/${pom.projectName}:${pom.projectVersion}'
            }
        }
    }
}