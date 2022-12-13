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
                  rm -fr lemoncode-calculadora
                  git clone https://github.com/srioboo/lemoncode-calculadora.git
                '''
            }
        }
        stage('compile') {
            steps {
                echo "Compilando código"
                sh '''
                  cd lemoncode-calculadora
                  ./gradlew compileJava
                '''
            }
        }

        stage('test') {
            steps {
                echo "Ejecutando test unitarios"
                sh '''
                  cd lemoncode-calculadora
                  ./gradlew test
                '''
            }
        }
    }
}    
