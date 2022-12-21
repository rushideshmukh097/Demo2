pipeline {
    agent {
        node {
            label 'SL1'
        }
    }

    stages {

        stage('build stage') {
            steps {
                sh 'yum install httpd -y'
                 }
        }

        stage('starting httpd') {
            steps {
                sh 'service httpd start'
            }
        }
       
        stage('redirect ') {
            steps {
             sh ' echo "This is job is build and deploy by slave-1 " >> /var/www/html/master.html '
            }
        }

        stage('permission ') {
            steps {
                sh 'chmod -R 777 /var/www/html/master.html'
            }
        }

        stage('restart') {
            steps {
                sh 'chkconfig httpd on'
            }
        }

      } 
}
       
   
