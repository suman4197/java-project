pipeline {
    agent any 
        stages { 
            stage ('cloning a repository') { 
                  steps {
                      git branch: 'main', url: 'https://github.com/suman4197/java-project.git'
                      echo "cloning is succesful"
                      }
                    }
             stage ('building a war file') { 
                    steps {
                        sh 'mvn clean install'
                        }
                     }
            stage ('deploting the war file ') {
                steps {
                    sh 'scp -r /home/ec2-user/.m2/repository/com/efsavage/hello-world-war/1.0.0/hello-world-war-1.0.0.war ssh ec2-user@172.31.4.208:/home/ec2-user/tomcat/apache-tomcat-8.5.75/webapps/'
                    echo"deployment is succesful"
                    }
                   }
                  }
                }
             
