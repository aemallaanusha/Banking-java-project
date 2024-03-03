pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/aemallaanusha/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with anusha'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile:compile'
            }
        }
        stage('codetesting with anusha'){
            steps{
                sh 'mvn test:test'
            }
        }
        stage('qa with anusha'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('package with anusha'){
            steps{
                sh 'mvn jar:jar'
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
