node {
    def app
    
    stage 'checkout' 
        git credentialsId: 'ads-git-amits', url: 'https://git.gbt.gbtad.com/ashar665/Jenkins-Samples.git'
    
    stage 'Maven build'
        sh 'ls'
        sh 'mvn -f spring-boot-hello/pom.xml clean install'
    
    
    stage 'build'
        echo 'Hello Build'
        app = docker.build("gbt/helloboot","-f spring-boot-hello/Dockerfile .")
    
    stage'Push image'
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         * Pushing multiple tags is cheap, as all the layers are reused. */
        docker.withRegistry('https://repos.gbt.gbtad.com:9443','NEXUS-REPO-CREDENTIALS') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
      
    

}