node {
    stage('Checkout') {
//        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/nurnberg/hello/']]])
        checkout scm
    }
    
    def mavenHome = tool name:'maven'

    stage('Build') {
        sh "${mavenHome}/bin/mvn -B clean package"
    }
    
    stage('Deploy') {
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('Test') {
        
    }
}
