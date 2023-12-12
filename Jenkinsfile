// Define the pipeline with an agent using a Docker image
pipeline {
  agent {
    docker { 
      // Specify the Docker image to use for the pipeline agent
      image 'node:16-alpine' 
    }
  }
  
  // Define stages within the pipeline
  stages {
    // Stage for testing
    stage('Test') {
      steps {
        // Execute a shell command to print Node.js version
        sh 'node --version'
      }
    }
  }
} 
