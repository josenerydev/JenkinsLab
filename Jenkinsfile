pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Iniciando o Build...'
                bat 'dotnet build'
            }
        }
        stage('Test') {
            steps {
                echo 'Executando Testes...'
                // Inclua seu comando de teste aqui, por exemplo:
                // bat 'dotnet test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Inclua seu comando de deploy aqui, se necessário
            }
        }
    }
    post {
        success {
            echo 'Build concluído com sucesso.'
        }
        failure {
            echo 'Build falhou.'
        }
    }
}
