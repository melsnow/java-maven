pipeline {
    agent any
    tools {
        maven 'Maven 3.9.8'
    }
    environment {
        MAVEN_HOME = tool name: 'Maven 3.9.8', type: 'maven'
        PATH = "${MAVEN_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
