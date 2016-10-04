node {
    stage('Checkout') {
//        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/nurnberg/hello/']]])
        checkout scm
    }
    
    def mavenHome = tool name:'m3'

    stage('Build') {
        sh "${mavenHome}/bin/mvn -B package"
    }
    
    stage('Deploy') {
        sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('Test') {
        
    }
}
