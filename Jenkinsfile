#!/usr/bin/env groovy


pipeline {
  agent any
	tools {
        gradle 'GradleAut'
        }
  stages {
    stage('Gradle Clean Test') {
      steps {
        sh 'gradle clean test'
        }
	  post {
        always {
        junit "build/test-results/test/TEST-org.gradle.examples.web.ServletTest.xml"
        }
		success {
		sh 'gradle war'
		}
	  } 
    }
  }
  post {
      success {
		archiveArtifacts artifacts: "build/libse/hello-world-app.war", fingerprint: true
		
      }
    }
}