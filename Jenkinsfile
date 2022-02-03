pipeline {
    agent any 
        stages { 
            stage ('cloning a repository') { 
              agent {label 'master'}
                  steps {
                      git branch: 'main', url: 'https://github.com/suman4197/java-project.git'
                      echo "cloning is succesful"
                      }
                    }
             stage ('building a war file') { 
                agent {label 'slave01'}
                    steps {
                        sh 'mvn clean install'
                        }
                     }
            stage ('deploting the war file ') {
                steps {
                    sh '/opt/jenkins/workspace/pip/target/hello-world-war-1.0.0.war ec2-user@172.31.4.208:/home/ec2-user/'
                    }
            }
                  }
                }
             
