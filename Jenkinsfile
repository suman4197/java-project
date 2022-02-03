pipeline {
    ageny any 
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
                  }
                }
             
