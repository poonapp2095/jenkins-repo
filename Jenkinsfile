pipeline {
    agent {
        label "built-in"
    }

    stages {
        stage ('Compile Stage') {

            steps {
                
                    sh 'mvn clean compile'
                }
            
        }

        stage ('Testing Stage') {

            steps {
                
                    sh 'mvn test'
                }
            
        }


        stage ('Install Stage') {
            steps {
                
                    sh 'mvn install'
                }
            
        }
        
        stage ('copy to tomcat') {

            steps {
                 sh "chmod -R 777 /mnt/servers/apache-tomcat-9.0.73/webapps/"
                  sh "cp -r /root/.jenkins/workspace/jenkins-repo_master/target/jenkins-example-1.0-SNAPSHOT.jar /mnt/servers/apache-tomcat-9.0.73/webapps/"
                }
            
        }
    }
}
