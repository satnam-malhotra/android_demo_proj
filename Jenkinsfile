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
                buildInfo = rtGradle.run rootDir: "circle-ci-android-demo-master/", buildFile: 'build.gradle', tasks: 'clean artifactoryPublish'
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
            cleanWs()
        }
    }
}