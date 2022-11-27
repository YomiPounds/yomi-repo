pipeline{
    agent {
        label{
            label'slave1'
        }
    }
    stages{
        stage('clone-stage'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-yomipounds', url: 'https://github.com/YomiPounds/yomi-repo.git']]])

            }
        }
        stage('parallel-stage'){
            parallel{
                stage('sub-para-stage'){
                    steps{
                        echo "trying again"
                    }
                }
                stage('sub-para2'){
                    agent{
                        label{
                            label'slave2'
                        }
                    }
                    steps{
                        sh 'pwd'
                    }
                }
            }
        }
        stage('main-stage2'){
            agent{
                label{
                    label'slave1'
                }
            }
            steps{
                echo "nice one"
            }
        }
        stage('closing-stage'){
            steps{
                echo "I made it laslas"
            }
        }
        stage('another-agent-stage'){
            agent{
                label{
                    label'slave2'
                }
            }
        }
    }
}
