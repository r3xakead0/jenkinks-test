pipeline {
    agent any
    environment{
		RELEASE_VERSION = "1.0.0"
    }
    stages {
        stage ('Hello') {
            steps {
                echo "Hello World ${RELEASE_VERSION}" 
            }
        }
        stage ('Invoke Child') {
            steps {
                build job: 'pipeline-child', 
                parameters: [
                    string(name: 'VERSION', value: "${RELEASE_VERSION}")
                ], 
                wait: true
            }
        }
        stage("Run script"){
            steps {
                script {
                    bat "echo Hello World"
                }
            }
        }
        stage ('Invoke Child with output') {
            steps {
                script 
                { 
                    buildResults = build job : "pipeline-child", 
                                parameters: [
                                    string(name: 'VERSION', value: "${RELEASE_VERSION}")
                                ], 
                                wait: true
                    println(buildResults.getBuildVariables()["MESSAGE"])    
                }         
            }
        }
    }
}