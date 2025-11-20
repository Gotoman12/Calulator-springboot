pipeline {
    agent any
    tools {
        jdk "java-17"
        maven "maven"
    }
    stages {
        stage('GIT-CHECKOUT') {
            steps {
                git branch: 'main', url: 'https://github.com/Gotoman12/Calulator-springboot.git'
            }
        }
        stage('Maven Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Maven Clean Package') {
            steps {
                sh 'mvn clean package'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
        stage('Host the Application in ec2') {
            steps {
                // This runs the app in the foreground—use with caution!
                sh 'nohup java -jar target/calculator-app-0.0.1-SNAPSHOT.jar &'
            }
        }
    }
}
