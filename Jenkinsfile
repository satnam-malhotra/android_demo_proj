pipeline {
    agent any

    stages {
        stage('Checkout') {
                steps {
                    echo 'Building..'
                }
            }
        stage('Build') {
            steps {
                sh './gradlew assemble'
                echo "The build stage passed..."
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post{
        always{
            echo "post-build will always run after build completed"
            // Jenkins cleans the workspace
            //cleanWs()
        }
    }
}