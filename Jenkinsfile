pipeline {
    agent {label: "Jenkins-Agent"}
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage('Cleanup Workspace'){
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Kiteretzu/production-devop'
            }
        }

        stage("Build Application") {
            steps {
                sh "mvn clean package"
            }
        }

        stage("Test application") {
            steps {
                sh "mvn test"
            }
        }
    }
}