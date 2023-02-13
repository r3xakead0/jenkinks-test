pipeline {
    agent any
    environment{
		RELEASE_VERSION = "1.0.0"
    }
    stages {
        stage ('First') {
            steps {
                echo "Hello World ${RELEASE_VERSION}" 
            }
        }
        stage ('Invoke Child') {
            steps {
                build job: 'pipeline-child', 
                parameters: [
                    string(name: 'VERSION', value: ${RELEASE_VERSION})
                ], 
                wait: true
            }
        }
    }
}