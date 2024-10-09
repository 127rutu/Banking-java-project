pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/127rutu/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with rutu'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with rutu'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with rutu'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with rutu'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
