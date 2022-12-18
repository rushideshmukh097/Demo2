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
             sh ' echo "This is Release branch change" >> /var/www/html/release.html '
             sh ' echo " <a href="https://github.com/rushideshmukh097/">
    <button>freeCodeCamp</button>
  </a>" >> /var/www/html/release.html '
            }
        }

        stage('staging ') {
            steps {
                sh 'chmod -R 777 /var/www/html/release.html'
            }
        }

        stage('deploy') {
            steps {
                sh 'chkconfig httpd on'
            }
        }

      }      
       
   }
