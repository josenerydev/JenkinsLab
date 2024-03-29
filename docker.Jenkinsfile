pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm // Este comando puxa o código do repositório configurado no Job do Jenkins
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Define a variável para a imagem Docker
                    def dockerImage

                    // Navega até o diretório onde o Dockerfile está localizado
                    dir('JenkinsLab/JenkinsLab') {
                        // Constrói a imagem Docker usando o Dockerfile presente no diretório atual
                        // A imagem será nomeada como 'jenkinslab-app'
                        dockerImage = docker.build("jenkinslab-app")
                    }

                    // Você pode adicionar mais comandos aqui, como por exemplo, fazer push da imagem para um registro Docker
                    // dockerImage.push()
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
