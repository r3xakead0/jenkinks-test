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
    }
}