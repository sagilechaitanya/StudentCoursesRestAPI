pipeline {
  agent {label'2'}
  triggers{
    pollSCM('* * * * *')
  }
  stages{
    stage('vcs') {
      steps{
        git url: 'https://github.com/sagilechaitanya/StudentCoursesRestAPI.git',
            branch: 'docker'
      }  
    }
    stage('build') {
      steps{
        sh 'docker image build -t chaitanyasagile/spc:latest .'
      }  
    }
    stage('scan'){
      steps{
        sh 'echo docker scan chaitanyasagile/spc:latest',
        sh 'docker image push chaitanyasagile/spc:latest'
      }  
    }
  }  
}