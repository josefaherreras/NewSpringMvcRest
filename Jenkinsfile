pipeline {
    agent any

    tools { 
        maven 'Maven 3.6.0' 
        jdk 'JDK 1.8'
    }

    stages {
        stage('Clean') {
        steps {
        sh 'mvn clean'
        script {
        if (currentBuild.result == 'SUCCESS') {
        env.BUILD_STAGE1_STATUS = 'SUCCESS'
        } else {
        env.BUILD_STAGE1_STATUS = 'FAILURE'
        }
    }
}
}

stage('Install') {
steps {
sh 'mvn install'
script {
if (currentBuild.result == 'SUCCESS') {
env.BUILD_STAGE2_STATUS = 'SUCCESS'
} else {
env.BUILD_STAGE2_STATUS = 'FAILURE'
}
}
}
}
}
}
