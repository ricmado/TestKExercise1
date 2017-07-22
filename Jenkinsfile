#!/usr/bin/env groovy


pipeline {
  agent any
	tools {
        gradle 'GradleAut'
        }
  stages {
    stage('build') {
      steps {
        sh 'gradle clean test'
        }
    }
    stage('run') {
      steps {
		echo env.JOB_NAME
		
      }
    }
  }
}