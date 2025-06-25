pipeline {
    agent { label 'TestAgent' }  // name of your agent node

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build the .NET') {
            steps {
                sh 'dotnet build'
            }
        }

        stage('Run tests') {
            steps {
                sh 'dotnet test'
            }
        }
    }

    post {
        always {
            echo 'Pipleline completed.'
        }
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
