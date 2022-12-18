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
                script {
             sh ' echo " <html>
<head>
<title>Page Title</title>
</head>
<body> <form>
  <label for="fname">First name:</label><br>
  <input type="text" id="fname" name="fname"><br>
  <label for="lname">Last name:</label><br>
  <input type="text" id="lname" name="lname">
</form> </body>
</html> " >> /var/www/html/release.html '
                }
             
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
