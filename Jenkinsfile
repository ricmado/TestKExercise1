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
		sucess {
		sh 'gradle war'
		}
	  } 
    }
    stage('Archive War') {
      steps {
		echo env.JOB_NAME
		
      }
    }
  }
  post {
      sucess {
		archive "build/libs/hello-world-app.war"
		
      }
    }
}