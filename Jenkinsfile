node {
    def app
    
    stage ‘checkout’{
        git url:’github.com/amitoncloud007/SpringBoot.git'
}
    
    stage ‘Maven build’{
        sh ‘mvn -f pom.xml clean install’
}
    
    stage ‘build’{
        echo ‘Hello Build’
}
}
