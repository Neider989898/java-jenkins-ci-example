pipeline {
    agent any
  //tools {
      //  maven 'Maven'
        // jdk 'JDK instalado'
    //}
    stages {
        stage('Clonar código') {
            steps {
                git url: 'https://github.com/Neider989898/java-jenkins-ci-example.git', branch: 'main'
            }
        }
        stage('Compilar') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn clean compile'
                    } else {
                        bat 'mvn clean compile'
                    }
                }
            }
        }
        stage('Pruebas') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn test'
                    } else {
                        bat 'mvn test'
                    }
                }
            }
        }
        stage('Empaquetar') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'mvn package'
                    } else {
                        bat 'mvn package'
                    }
                }
            }
        }
    }
    post {
        success {
            echo ' La compilación y las pruebas fueron exitosas.'
        }
        failure {
            echo 'Hubo errores en la compilación o en las pruebas.'
        }
    }
}