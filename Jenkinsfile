pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore'
            }
        }
        
        stage('Build the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage('Run all tests for the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test --no-build --no-restore'
            }
        }
    }
}