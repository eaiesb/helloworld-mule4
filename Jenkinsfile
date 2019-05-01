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
          buildsrc() 
      }
}
    }
dir ('.' ) {
     sh '/usr/maven/apache-maven-3.3.9/bin/mvn clean package mule:deploy -Dmyenv=DEV'
}
}

