pipeline {
    agent any

    stages {

        stage('build stage') {
            steps {
                sh 'yum install httpd -y'
                 }
        }

        stage('1st testing') {
            steps {
                sh 'service httpd start'
            }
        }
       
        stage('2nd testing ') {
            steps {
             sh ' echo " Build is trigger by WebHook" >> /var/www/html/qa.html '
            }
        }

        stage('staging ') {
            steps {
                sh 'chmod -R 777 /var/www/html/qa.html'
            }
        }

        stage('deploy') {
            steps {
                sh 'chkconfig httpd on'
            }
        }

      }      
       
   }
