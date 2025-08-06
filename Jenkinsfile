pipeline {
    agent any

    tools {
        nodejs "nodejs"
    }

    stages {
        stage("Install Dependencies") {
            steps {
                sh 'npm install'
            }
        }

        stage("Build App") {
            steps {
                sh 'npm run build'
            }
        }

        stage("Start Server") {
            steps {
                sh 'nohup npm run start &'
            }
        }
    }

    post {
        success {
            echo "✅ BUILD & RUN SUCCESSFUL"
        }
        failure {
            echo "❌ BUILD FAILED"
        }
    }
}
