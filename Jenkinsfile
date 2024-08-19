pipeline {
    agent any
    //agent {
      //  docker {
        //    image '61bbb301b0da' // Replace with your actual Docker image name and tag
          //  args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
        //}
    
    environment {
        ANDROID_HOME = '/Users/apple/Library/Android/sdk' // Replace with the actual path to your Android SDK
        GRADLE_USER_HOME='/Users/apple/softwares/gradle-7.5/bin'
        //PATH = "${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools:${env.PATH}"
        PATH = "/opt/homebrew/opt/openjdk@11/bin:/Users/apple/softwares/gradle-7.5/bin:/Users/apple/Library/Android/sdk/build-tools/33.0.3:$PATH"
        DOCKER_HOME = "/usr/local/bin" // Set this to your Docker installation path
    }
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                git branch: 'main', url: 'https://github.com/sathamhussain123/ample-todo-android-app-001.git'
            }
        }

        stage('Build') {
            steps {
                // Give execution permission to the gradlew script
        sh 'chmod +x ./gradlew'
                
                // Build the Android app
                // sh "./gradlew wrapper --gradle-version 7.5"
                //sh './gradlew assembleDebug --no-daemon --stacktrace'

                //sh './gradlew assembleDebug'
                sh './gradlew build'
            }
        }
    }

    post {
        always {
            // Clean up the workspace after the build
            cleanWs()
        }
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
