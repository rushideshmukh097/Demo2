pipeline {
    agent {
        label{
            label 'SL2'
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
             sh ' echo "This is dev branch code change-1 & build is trigger by WebHook & job is build and deploy by slave-2 " > /var/www/html/master.html '
            }
        }

        stage('permission ') {
            steps {
                sh 'sudo chmod -R 777 /var/www/html/master.html'
            }
        }

        stage('restart') {
            steps {
                sh 'sudo chkconfig httpd on'
            }
        }

      } 
}
