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
             sh ' echo "this is dev branch change" >> /var/www/html/dev.html '
            }
        }

        stage('staging ') {
            steps {
                sh 'chmod -R 777 /var/www/html/dev.html'
            }
        }

        stage('deploy') {
            steps {
                sh 'chkconfig httpd on'
            }
        }

      }      
       
   }
