pipeline {
    agent any

    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'staging', 'prod'], description: 'Select the environment to deploy')
    }

    stages {
        stage('Print Selected Environment') {
            steps {
                echo "Selected Environment: ${params.ENVIRONMENT}"
            }
        }

        stage('Conditional Execution') {
            steps {
                script {
                    if (params.ENVIRONMENT == 'dev') {
                        echo "Deploying to Development environment"
                        // Add dev deployment logic here
                    } else if (params.ENVIRONMENT == 'staging') {
                        echo "Deploying to Staging environment"
                        // Add staging deployment logic here
                    } else if (params.ENVIRONMENT == 'prod') {
                        echo "Deploying to Production environment"
                        // Add production deployment logic here
                    } else {
                        error("Invalid environment selected!")
                    }
                }
            }
        }
    }
}
