pipeline{
    agent any
        stages{
            stage('cloning-from-jui'){
                steps{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'jenkinsgit', url: 'https://github.com/YomiPounds/yomi-repo.git']]])
                }
            }
            stage('parallel-main-stage'){
                parallel{
                    stage('parallel-sub-stage'){
                        steps{
                            sh 'whoami'
                        }
                    }
                    stage('parallel-stage2'){
                        steps{
                            echo "hopefully this works"
                        }
                    }
                }
            }
            stage('main-stage2'){
                steps{
                    sh 'pwd'
                }
            }
        }
}
