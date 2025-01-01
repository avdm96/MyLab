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

        //Stage3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '66ed4f6e-f20d-471b-95eb-c82864178942', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.117', nexusVersion: 'nexus3', protocol: 'http', repository: 'AntoniosDevOpsLab-SNAPSHOT', version: '0.0.4-SNAPSHOT'

            }
        }
		

		 // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }     
    }

}