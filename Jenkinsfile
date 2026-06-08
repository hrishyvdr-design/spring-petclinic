pipeline {
    agent any

    tools {
        maven 'Maven3' // ഇതിന്റെ സെറ്റപ്പ് നമ്മൾ അടുത്ത ഘട്ടത്തിൽ ജെങ്കിൻസിൽ ചെയ്യും
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                // ഗിറ്റ്ഹബ് കോഡ് ജെങ്കിൻസ് ഓട്ടോമാറ്റിക് ആയി എടുത്തോളും
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
                // സൊണാർക്യൂബ് സ്റ്റെപ്പ് നമ്മൾ പിന്നീട് ആഡ് ചെയ്യും
            }
        }

        stage('Upload to Nexus') {
            steps {
                echo 'Uploading Build Artifact (.jar file) to Nexus...'
                // നെക്സസ് സ്റ്റെപ്പ് നമ്മൾ പിന്നീട് ആഡ് ചെയ്യും
            }
        }
    }
}
