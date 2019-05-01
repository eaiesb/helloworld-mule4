#!/usr/bin/groovy
pipeline {
    environment {
        JAVA_HOME = tool('java')
    }
agent any
options {
disableConcurrentBuilds()
}
stages {
  
stage("Build Mule Source Code") {
steps {
          slackSend (color: "#f1502f", message: "Git URL is : ${env.GIT_URL}")
          slackSend (color: "add8e6", message: 'salesforce-newcustomer Deployment Started')
          buildsrc() 
      }
}

}
   
}
// steps
def buildsrc() {
dir ('.' ) {
     sh '/devops/maven/apache-maven-3.3.9/bin/mvn clean package mule:deploy -Dmyenv=dev'
}
}
