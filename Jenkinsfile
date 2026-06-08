pipeline {
    agent any

    tools {
        maven 'Maven3'
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
                // ജെങ്കിൻസിൽ നമ്മൾ കൊടുത്ത 'SonarQube' എന്ന പേര് ഇവിടെ കൃത്യമായി നൽകണം
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Upload to Nexus') {
            steps {
                echo 'Uploading Build Artifact (.jar file) to Nexus...'
                // നെക്സസ് സ്റ്റെപ്പ് നമ്മൾ അടുത്ത ഘട്ടത്തിൽ ചെയ്യും
            }
        }
    }
}
