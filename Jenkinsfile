pipeline{
    agent{
        node{
            label 'master'
        }
    }
    tools{
        maven 'maven-3.3.1'
    }
    options{
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableResume()
        disableConcurrentBuilds()
        timestamps()
        timeout(time: 1, unit: 'HOURS')
    }
    stages{
        stage('Pre-check'){
            steps{
                sh 'mvn --version'
		sh 'pwd'
            }
        }
        stage('Build'){
            steps{
                dir("${WORKSPACE}"){
                    sh 'mvn clean package'
                }
            }
        }
    }
}
