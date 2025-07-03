pipeline {
    agent {
        label 'window'
    }
    tools {
        maven 'maven 3.6.0'
    }
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm') {
            steps {
                git branch: 'bugfix-branch-2', url: 'https://github.com/dhanu0395/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 bat 'mvn clean install'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Bugfix deployed! for webhook testing'
                // Add your deploy steps here
            }
        }

        
    }

  post{

  success{
     echo 'Build success'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
