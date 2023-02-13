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
        stage ('Second') {
            steps {
                echo "Second step" 
            }
        }
        stage ('Invoke Child') {
            steps {
                build job: 'pipeline-child', 
                parameters: [
                    string(name: 'VERSION', value: "1.0.1")
                ]
            }
        }
    }
}