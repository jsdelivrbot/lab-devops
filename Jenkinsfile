#!groovy

pipeline {
	agent{
		node {
		    label 'node' 
 			}
		}
	}


    currentBuild.result = "SUCCESS"

    try {

       stage('Git Clone'){

          sh 'git clone https://github.com/githublab-ph/lab-devops.git'
          sh 'cd lab-devops'
       }

       stage('Build Node App'){
	sh 'npm install'
        sh 'npm run build'
        sh 'cd build'
       }

       stage('Start Application'){

            sh 'npm start'
       }

       stage('Deploy'){
	sh 'pwd'
	sh 'ls'

        }
            
    }


