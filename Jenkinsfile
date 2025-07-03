pipeline {
    agent {
        label 'linux_slave'
    }
    tools{
        maven 'maven 3.6.0'
    }
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm') {
            steps {
                git branch: 'deploy-branch-4', url: 'https://github.com/dhanu0395/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
stage('deloy'){
   steps{
       echo 'Deploying for branch-4'
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
