ennode {
    stage('git checkout') {
    git 'https://github.com/Hrkrishna5955/pipeline.git'
}
stage('Build') {
    sh 'mvn package'
}
  stage('Deployment')
{
    deploy adapters: [tomcat9(credentialsId: 'tomcat-credentialis', path: '', url: 'http://172.31.29.21:8080')], contextPath: 'qaapp', war: '**\\*.war'
}
 stage('testing'){
     git 'https://github.com/Hrkrishna5955/Functional-Testing.git'
     sh 'java -jar /var/lib/jenkins/workspace/scripted_pipeline/testing.jar'
 }
    stage('Delivery'){
        deploy adapters: [tomcat9(credtialsId: 'tomcat-credentialis', path: '', url: 'http://172.31.19.88:8080')], contextPath: 'Prodapp', war: '**\\*.war'
    }
}
