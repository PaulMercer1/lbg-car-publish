pipeline{

agent any   
        stages {
            stage ('Deploy'){
                steps{
                    script{
                        sshPublisher(publishers: [sshPublisherDesc(configName: 'TargetDockerServer',
                         transfers: [sshTransfer(cleanRemote: false, excludes: '', 
                         execCommand: 'docker stack deploy -c /home/jenkins/docker-compose.yaml cars', 
                         execTimeout: 120000, flatten: false, makeEmptyDirs: false, 
                         noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '',
                         remoteDirectorySDF: false, removePrefix: '', 
                         sourceFiles: 'docker-compose.yaml')], usePromotionTimestamp: false, 
                         useWorkspaceInPromotion: false, verbose: false)])
                    }
                }
            }
        }
}

