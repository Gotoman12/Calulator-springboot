pipeline{
    agent any
    tools{
       jdk "java-17"
       maven "maven"
    }
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
        stage("host the application"){
            steps{
                sh "java -jar target/calculator-app-0.0.1-SNAPSHOT.jar"
            }
        }
    }
}