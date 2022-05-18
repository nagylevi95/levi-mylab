pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 publish the artifacts to nexus
        stage ('Publish to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'LeviDevOpsLab', classifier: '', file: 'target/LeviDevOpsLab-0.0.4.war', type: 'war']], credentialsId: '3a2cd95e-faa7-45d0-b7d6-c46212dcb6f9', groupId: 'com.levisdevopslab', nexusUrl: '192.20.10.138:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'LeviDevopsLab-SNAPSHOT', version: '0.0.4'
            }
        }

        // Stage4 : Deploy
        stage ('Deploy'){
            steps {
                echo ' Deploying.... '

            }
        }

        
        
    }

}