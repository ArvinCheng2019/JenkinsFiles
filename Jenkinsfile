pipeline{
  agent any
  parameters{
    string(name:' str', defaultValue:'Default' ,description:"默认参数", trim:true)
    booleanParam(name:"bool", defaultValue:true,description:" 这是一个bool 参数")
    choice(name:' chs', choices:['ios','android','ps4'], description:" 这是一个选项")
    text(name:'text', defaultValue:'文本参数默认值',description:" 这是一个文本选项")
  }

  options{
    disableConcurrentBuilds() // 禁止多条流水线
    timestamps()
    //timeout(time:5,unit:'SECONDS') 超时 可以 timeout(5) 这种是 5分钟
  }

environment{
  foo = 'today is friday'
}

  stages{
    stage('获取参数'){
      steps{
        sh label:' ',script:"echo ${params.str}"
        sh label:' ',script:"echo ${params.bool}"
        sh label:' ',script:"echo ${params.chs}"
        sh label:' ',script:"echo ${params.text}"
        sh label:' ',script:"echo ${foo}"
      }
    }

    stage('打包'){
      steps{
        sh label:' ',script:' echo build'
        script{
          
        }
      }
    }
    stage('发布'){
        steps{
          sh label:' ',script:" echo release"
        }
      }
  }
}
