node {
    def app
    
    stage ‘ßcheckout’
        git credentialsId: ‘Amit cloud’, url: ‘https://github.com/amitoncloud007/SpringBoot.git'
    
    stage ‘Maven build’
        sh ‘mvn -f pom.xml clean install’
    
    stage ‘build’
        echo ‘Hello Build’
}
