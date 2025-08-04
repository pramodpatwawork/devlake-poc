pipeline {
    agent any
    tools {
        jdk 'jdk21' // Name as configured in Global Tool Configuration
        gradle 'gradle8143' // Name as configured in Global Tool Configuration
    }
	
    stages {
        stage('Build') {
            steps {
                gradle clean build
            }
        }
    }
}