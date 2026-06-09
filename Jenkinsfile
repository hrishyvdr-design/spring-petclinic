pipeline {
    agent any

    tools {
        maven 'Maven3' // Loading Maven tool configured in Jenkins
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
            }
        }

        stage('Build & Test') {
            steps {
                echo 'Building Java Application using Maven...'
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Running Code Quality Check via SonarQube...'
                // Using the server named 'SonarQube' that we created in Jenkins settings
                withSonarQubeEnv('SonarQube') {
                    // Maven will automatically trigger the sonar scan
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Upload to Nexus') {
            steps {
                echo 'Uploading Build Artifact (.jar file) to Nexus...'
            }
        }
    }
}
