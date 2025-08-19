pipeline {
    agent any

    stages {
        stage('Checkout repository') {
            steps {
                checkout scm
            }
        }
        stage('Setup .NET') {
            steps {
                bat 'dotnet --version' // Verifies .NET is installed
            }
        }
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}