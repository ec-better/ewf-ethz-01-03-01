<<<<<<< HEAD
node('ci-community') {
  
  stage 'Checkout'
  checkout scm
  
  stage 'Setup environment'
  env.PATH = "${tool 'apache-maven-3.0.5'}/bin:/opt/anaconda/bin:${env.PATH}"
  
  stage 'Package and Deploy'
  sh 'mvn deploy'
=======
pipeline {
>>>>>>> a08266dd56242a148ee49e133b85468d99571ef5

  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }

  environment {
        PATH="/opt/anaconda/bin:/opt/anaconda/bin:/opt/anaconda/bin:/usr/lib64/qt-3.3/bin:/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/home/fbrito/bin"
  }

  agent {
    node {
      label 'ci-community-docker'
    }
  }

  stages {

    stage('Package & Dockerize') {
      steps {
        withMaven( maven: 'apache-maven-3.0.5' ) {
            sh 'mvn -B deploy'
        }
      }
    }
  }
}
