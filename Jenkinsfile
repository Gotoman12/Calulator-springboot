pipeline{
    agent any
    stages{
        stage("GIT-CHECKOUT"){
            steps{
                git branch:"main",url:"https://github.com/Gotoman12/Calulator-springboot.git"
            }
        }
        stage("maven test"){
            steps{
                sh "mvn test"
            }
        }
        stage("maven clean package"){
            steps{
                sh "mvn clean package"
            }
        }
    }
}