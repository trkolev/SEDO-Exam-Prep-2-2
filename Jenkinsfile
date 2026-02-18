pipeline{
    agent any
    environment {
        PATH = "/usr/local/share/dotnet:${env.PATH}"
    }
    stages{
        stage('Restore'){
            steps{
                echo 'Restoring dependencies...'
                sh 'dotnet restore'
            }
        }
        stage('Build'){
            steps{
                echo 'Building the application...'
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test'){
            steps{
                echo 'Running tests...'
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}