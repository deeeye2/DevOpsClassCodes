pipeline {
  agent any
  stages {
    stage('version') {
      parallel {
        stage('version') {
          steps {
            sh '''mvn --version
git --version
java -version'''
          }
        }

        stage('check for pom') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('build') {
      steps {
        sh 'mvn compile test package'
      }
    }

    stage('post build steep') {
      steps {
        writeFile(file: 'status.txt', text: 'its works')
      }
    }

  }
}