pipeline {
    agent any

    when {
        branch 'main'
    }
    
    stages {
        stage('Restore dependencies') {
            
            steps {
                bat 'dotnet restore'
            }
        }
        
        stage('Build the project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage('Run all tests for the project') {
            steps {
                bat 'dotnet test --no-build --no-restore'
            }
        }
    }
}