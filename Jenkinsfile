pipeline {
    agent any
    
    

    stages {


        stage ('Build') {
            steps {
                script {
                    System.setProperty("org.jenkinsci.plugins.durabletask.BourneShellScript.LAUNCH_DIAGNOSTICS", true);
                }
                
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
                
                
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
