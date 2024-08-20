pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/jenkins_home/workspace:/workspace -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker run -v /workspace:/app satham:v2 gradle build'
            }
        }
    }
}


// ================================
// pipeline {
//     agent none
//     stages {
//         stage('Build') {
//               agent {
//                docker {
//              image 'satham:v2' // Replace with your actual Docker image name and tag
//                     reuseNode true // Reuse the node Jenkins is running on
//       }
//               }      
            
//             environment {
//                 ANDROID_HOME = '/Users/apple/Library/Android/sdk'
//                 GRADLE_USER_HOME='/Users/apple/softwares/gradle-7.5/bin'
//                 PATH = "/opt/homebrew/opt/openjdk@11/bin:/Users/apple/softwares/gradle-7.5/bin:/Users/apple/Library/Android/sdk/build-tools/33.0.3:$PATH"
//             }
//             steps {
//                 script {
//                     docker.image('61bbb301b0da').inside('-v /var/run/docker.sock:/var/run/docker.sock') {
//                         // Clone the repository
//                         git branch: 'main', url: 'https://github.com/sathamhussain123/ample-todo-android-app-001.git'

//                         // Set up environment
//                         sh 'chmod +x ./gradlew'

//                         // Build the Android app
//                         sh './gradlew build'
//                     }
//                 }
//             }
//         }
//     }
//     post {
//         success {
//             echo 'Build completed successfully!'
//         }
//         failure {
//             echo 'Build failed!'
//         }
//     }
// }



// =================================================================================
//First Script

// pipeline {
//     //agent any
//     agent {
//         docker {
//             image 'satham:v2' // Replace with your actual Docker image name and tag
//            // args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
//         }
//     }
//     environment {
//         ANDROID_HOME = '/Users/apple/Library/Android/sdk' // Replace with the actual path to your Android SDK
//         GRADLE_USER_HOME='/Users/apple/softwares/gradle-7.5/bin'
//         //PATH = "${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools:${env.PATH}"
//         PATH = "/opt/homebrew/opt/openjdk@11/bin:/Users/apple/softwares/gradle-7.5/bin:/Users/apple/Library/Android/sdk/build-tools/33.0.3:$PATH"
//         DOCKER_HOME = "/usr/local/bin" // Set this to your Docker installation path
//     }
//     stages {
//         stage('Clone Repository') {
//             steps {
//                 // Clone the repository
//                 git branch: 'main', url: 'https://github.com/sathamhussain123/ample-todo-android-app-001.git'
//             }
//         }

//         stage('Build') {
//             steps {
//                 // Give execution permission to the gradlew script
//         sh 'chmod +x ./gradlew'
                
//                 // Build the Android app
//                 // sh "./gradlew wrapper --gradle-version 7.5"
//                 //sh './gradlew assembleDebug --no-daemon --stacktrace'

//                 //sh './gradlew assembleDebug'
//                 sh './gradlew build'
//             }
//         }
//     }

//     post {
//         always {
//             // Clean up the workspace after the build
//             cleanWs()
//         }
//         success {
//             echo 'Build completed successfully!'
//         }
//         failure {
//             echo 'Build failed!'
//         }
//     }
// }
