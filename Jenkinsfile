pipeline {
    agent any

    environment {
        DEMO='1.3'
    }

    stages {
        stage('checkout') {
            steps {
                echo "Descargando código del repositorio"
                sh '''
                  git clone url-repositorio
                '''
            }
        }
        stage('compile') {
            steps {
                echo "Compilando código"
                sh '''
                  ./gradlew compileJava
                '''
            }
        }
        
        stage('test') {
            steps {
                echo "Ejecutando test unitarios"
                sh '''
                  gradlew test
                '''
            }
        }
    }
}
