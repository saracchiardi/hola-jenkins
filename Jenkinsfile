
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Preparando aplicacion'
                sh 'python3 -m py_compile hola.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Ejecutando Hello World'
                sh 'python3 hola.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Desplegando en entorno de prueba'
                sh 'mkdir -p entorno-pruebas'
                sh 'cp hola.py entorno-pruebas/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado correctamente'
        }
        failure {
            echo 'Error durante la ejecucion'
        }
    }
}

