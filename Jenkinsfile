pipeline {
    agent any

    stages {
        stage('Clonar código') {
            steps {
                git url: 'https://github.com/TU_USUARIO/java-jenkins-ci-example.git', branch: 'main'
            }
        }
        stage('Compilar') {
            steps {
                bat 'mvn clean compile'
            }
        }
        stage('Pruebas') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                bat 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'La compilación y las pruebas fueron exitosas.'
        }
        failure {
            echo 'Hubo errores en la compilación o en las pruebas.'
        }
    }
}
