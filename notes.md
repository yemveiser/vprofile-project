Project Steps
..........................
Install Ubuntu 20 server
Install Jenkins application
Install Oracle JDK 
--configure oracle jdk in jenkins.
--point to path in JAVA_HOME: /usr/lib/jvm/java-1.8.0-openjdk-amd64

Configure maven for deploy.

Install plugins for pipeline integration for maven
--------------------------------

Pipeline utility steps
pipeline maven integration

Jenkins Script
````
pipeline {
    agent any
    stages {
        stage('Fetch code'){
            steps {
                git branch: 'paac', url: 'https://github.com/yemveiser/vprofile-project.git'
            }
        }
        stage('Build'){
            steps {
                sh 'mvn install'
            }
        }
        stage(Test){
            steps {
                sh 'mvn test'
            }

        }
    }
}
````
