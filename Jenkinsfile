pipeline {
    agent none
    stages {
        stage('Non_parallel Stage') {
            agent {
                label "master"
            }
            steps {
                echo "this stage will be executed first"
            }
        }
        stage('Run Tests'){
            parallel {
                stage('Test on Linux') {
                    agent {
                        label "linux_node"
                    }
                    steps {
                        echo "task1 on agent"
                        sh "echo 'new' > agent.txt"
                    }
                }
                stage ('Test on Master') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "task1 on master"
                        sh "echo 'new' > master.txt"
                    }
                }
                
            }
        }
    }
}
