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
                     version = pom.version
                    sh 'mvn clean package dockerfile:build'
                    sh "echo ${version}"
                }

                //sh "docker push levietthang1997/${projectName}:${projectVersion}"
            }
        }
    }
}