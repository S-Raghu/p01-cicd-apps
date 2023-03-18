pipeline{
    agent{
        label{
            label "java-slave"
        }
    }
    tools{
        maven "M2_HOME"
    }
    stages{
        stage('Git'){
            steps{
                checkout changelog:checkout scmGit(branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: 'ebf15a19-61ff-44cb-9079-6aebbc010096', url: 'https://github.com/S-Raghu/p01-cicd-apps.git']])
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
        }
    }
}
