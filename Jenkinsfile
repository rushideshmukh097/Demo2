pipeline {
    agent {
        label{
            label 'SL1'
        }
    }

    stages {

        stage('build stage') {
            steps {
                sh 'sudo yum install httpd -y'
                 }
        }

        stage('starting httpd') {
            steps {
                sh 'sudo service httpd start'
            }
        }
       
        stage('redirect ') {
            steps {
             sh ' echo "This is QA branch commit-1 code change. Build is trigger by WebHook job is build and deploy by slave-1 " > /var/www/html/qa.html '
            }
        }

        stage('permission ') {
            steps {
                sh 'sudo chmod -R 777 /var/www/html/qa.html'
            }
        }

        stage('restart') {
            steps {
                sh 'sudo chkconfig httpd on'
            }
        }

      } 
}
