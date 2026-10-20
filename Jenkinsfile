pipeline{
    agent{
        label "node"
    }
    stages{
        stage("Restore dependencies"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet restore" // Restore dependencies for Windows machines
            }
        }
        stage("Build the project"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet build --no-restore" // Build the project for Windows machines
            }
        }
        stage("Run tests"){
            when {
                anyOf {
                    branch "main"
                    branch "develop"
                }
            }
            steps{
                bat "dotnet test --no-build --verbosity normal" // Run tests for Windows machines
            }
        }
    }
}