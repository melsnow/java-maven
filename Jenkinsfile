pipeline {
    agent any
    environment {
        MAVEN_HOME = tool name: 'Maven 3.9.8', type: 'maven'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        // other stages
    }
}
