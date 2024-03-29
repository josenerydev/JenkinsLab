pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm // Este comando puxa o código do repositório configurado no Job do Jenkins
            }
        }

        stage('Build') {
            steps {
                echo 'Iniciando o Build...'
                // Comando para construir a imagem Docker
                script {
                    // O Dockerfile está dentro do subdiretório JenkinsLab/JenkinsLab, então precisamos navegar até lá
                    dir('JenkinsLab/JenkinsLab') {
                        // Comando para construir a imagem Docker, nomeando a imagem como 'jenkinslab-app'
                        bat 'docker build -t jenkinslab-app .'
                    }
                }
            }
        }

        // Inclua outros estágios como Testes e Deploy conforme necessário

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
