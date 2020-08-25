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
                    def pom = readMavenPom file: 'pom.xml'
                    sh 'mvn clean package dockerfile:build'
                    sh "echo ${pom}"
                    sh "echo ${pom.projectName}"
                }

                //sh "docker push levietthang1997/${projectName}:${projectVersion}"
            }
        }
    }
}