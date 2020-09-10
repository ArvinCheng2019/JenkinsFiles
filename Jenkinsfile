pipeline{
  agent any
  stages{
    stage('打包'){
      steps{
        sh label:' ',script:' echo build'
      }
    }
    stage('发布'){
        steps{
          sh label:' ',script:" echo release"
        }
      }
  }
}
