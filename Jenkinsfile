@Library('piper-lib-os') _
node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
        mtaBuild script: this
    }
    stage('deploy') {
        withEnv(['HOWZZAT=its In']){
            cloudFoundryDeploy script: this
        }
    }
}