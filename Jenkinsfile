pipeline{
    agent any
    environment{
        DIRECTORYPATH = "DIRECTORY_PATH"
        TESTINGENVIRONMENT = "TESTING_ENVIRONMENT"
        PRODUCTIONENVIRONMENT = "Nira"
    }
    stages{
        stage('Build'){
            steps{
                echo "Building the code using Maven"
            }
        }
        stage(' Unit and integration Tests'){
            steps{
                echo "Running unit tests and integration tests"
            }
            post{
                success{
                    mail to: "nirajain2104@gmail.com",
                    subject: "test status email",
                    body: "Test is completed"
                }
            }
        }
        stage('code analysis'){
            steps{
                echo "Performing code analysis"
            }
        }
        stage('Security scan'){
            steps{
                echo "Performing security scan"
            }
            post{
                success{
                    mail to: "nirajain2104@gmail.com",
                    subject: "security scan stage ${currentBuild.result}",
                    body: "security scan completed"
                }
            }
        }
        stage('Deploy to staging'){
            steps{
                echo "Deploying to Staging environment"
            }
        }
        stage ('Integration Tests on staging'){
            steps{
                echo "Running integration tests on staging"
            }
        }
        stage ('Deploy to Production'){
            steps{
                echo "Deploying to Production environment"
            }
        }
    }
}