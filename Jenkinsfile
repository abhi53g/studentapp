pipeline {
    agent any

    tools {
        // Specify the Maven installation configured in Jenkins Global Tool Configuration
        maven 'MAVEN_HOME'
    }

    stages {
        stage('Git Clone & Clean') {
            steps {
                // Remove the project folder if needed (uncomment if required)
                // bat "rmdir /s /q your-project-folder"

                // Clone your GitHub repository - replace the URL with your actual repo
                bat "git clone https://github.com/your-username/your-repo.git"

                // Run 'mvn clean' in your project folder - replace 'your-repo' with actual folder name
                bat "mvn clean -f your-repo"
            }
        }

        stage('Install') {
            steps {
                // Run 'mvn install' to build the project and download dependencies
                bat "mvn install -f your-repo"
            }
        }

        stage('Test') {
            steps {
                // Run tests
                bat "mvn test -f your-repo"
            }
        }

        stage('Package') {
            steps {
		bat "mvn package -f your-repo"
            }
        }
    }
}
