node{

    echo "job name is: ${env.JOB_NAME}"
    echo "node name is: ${env.NODE_NAME}"
    
    def mavenhome = tool name: 'maven3.8.5'
    //get the code from github repo
    stage('checkoutcode'){
     git branch: 'development', credentialsId: '60570728-c90d-458e-af71-3fe33506d77b', url: 'https://github.com/anm-naveenteam/maven-web-application.git'   
    }
    //do the build by using maven build tool
    stage('build'){
    sh "${mavenhome}/bin/mvn clean package"
    }
    /*
    //execute the sonarqube report
    stage('executesonarqubereport'){
    sh "${mavenhome}/bin/mvn sonar:sonar"
    }
    //upload artifacts into artifactory repo
    stage ('uploadartifactsintonexus'){
    sh "${mavenhome}/bin/mvn deploy"
    }
    //deploy application into tomcat server
    stage ('deployapplicationintotomcatserver'){
    sshagent(['491349ac-76b6-4f9a-9036-829bf41bfca1']) {
    sh "scp -o strictHostkeychecking=no target/maven-web-application.war ec2-user@15.206.187.247:/opt/apache-tomcat-9.0.62/webapps/"
}

}
*/
}
