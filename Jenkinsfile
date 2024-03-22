pipeline {
  agent {
    docker {
      image 'jenkins-101'
      args 'C:\\apps\\jenkins\\jenkins-101'
    }

  }
  stages {
    stage('in') {
      steps {
        sh '''echo PATH = ${PATH}
echo M2_HOME = ${M2_HOME}
mvn clean'''
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }

    stage('Report') {
      steps {
        junit 'C:\\apps\\jenkins\\jenkins-101'
      }
    }

    stage('') {
      steps {
        archiveArtifacts 'C:\\apps\\jenkins\\jenkins-101'
      }
    }

  }
}