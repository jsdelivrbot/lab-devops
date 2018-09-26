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

  catch (err) {
	  currentBuild.result = "FAILURE"

            mail body: "project build error is here: ${env.BUILD_URL}" ,
            from: 'paulo.souza@dextra-sw.com',
            to: 'paulo.souza@dextra-sw.com',
            subject: 'project build failed',

        throw err
	}


