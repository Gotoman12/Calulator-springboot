pipeline{
    agent any

    stages{
        stage('git-chechout'){
            steps{
                git branch:'testing', url:'https://github.com/ManojKRISHNAPPA/Calulator-springboot.git'
            }
        }

        stage('test'){
            steps{
                sh '''
                    mvn test
                '''
            }
        }
        stage('packging'){
            steps{
                sh '''
                    mvn package
                '''
            }
        }
    }
}