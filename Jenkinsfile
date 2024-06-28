pipeline {
    agent {
        docker { image 'python:3' }
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clona o repositório Git especificando o branch 'main'
                git branch: 'main', url: 'https://github.com/eduardo7321/estudandoJenkins'
            }
        }

        stage('Run Python Function') {
            steps {
                script {
                    // Executa o script Python e armazena o resultado na variável 'result'
                    def result = sh(script: 'python3 script.py', returnStdout: true).trim()
                    // Imprime o resultado no log do próximo step
                    echo "Result from Python script: ${result}"
                }
            }
        }
    }
}
