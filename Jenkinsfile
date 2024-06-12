pipeline {
    agent any
    environment {
        //be sure to replace "kakrahanson" with your own Docker Hub username
        DOCKER_IMAGE_NAME = "kakrahanson/train-schedule"
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code from the repository'
                // Assuming you are using a Git repository, add the checkout step
                git 'https://github.com/your-repo/train-schedule.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
