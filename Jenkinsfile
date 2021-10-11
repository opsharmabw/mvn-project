pipeline {
        agent {label '3rdcentos'}
        stages {
            stage('code pulling') {
                steps {
                    git branch: 'dev', credentialsId: '5ccf38b4-a579-4801-b266-2ee29b107e76', url: 'https://github.com/opsharmabw/mvn-project.git'
                }
                }
            stage('maven clean') {
                steps {
                    sh 'mvn clean install'
                }
            }
            stage('maven build') {
                steps {
                    sh 'mvn package'
                }
            }
            stage('execute') {
                steps {
                    sh 'java -jar target/*.jar'
                }
            }
        }
}
