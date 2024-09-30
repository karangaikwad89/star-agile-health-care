pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/karangaikwad89/star-agile-health-care'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with karan'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with karan'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with karan'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with karan'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimglatest .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8095:8095 --name c003 myimglatest'
            }
        }   
    }
}
