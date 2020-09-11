pipeline{
  agent any
  parameters{

    string(name:'PROJ_PATH', defaultValue:'Default' ,description:"项目工程路径", trim:true)
    string(name:'UNITY_PATH', defaultValue:'Default' ,description:"Unity安装路径", trim:true)
    string(name:'EXPORT_PATH',defaultValue:'Default',description:'项目导出路径')
    string(name:'LOG_PATH',defaultValue:'Default',description:'打包log 的路径')
    string(name:'BUILD_AB',defaultValue:'JenkinsBuilder.BuildAndroidAB',description:'打AB 包的函数')
    choice(name:'RUN_FUN',choices:['JenkinsBuilder.BuildAndroid_UWA','JenkinsBuilder.BuildAndroid_Full'], description:"这里是可执行函数,对应Unity里的函数")
  }

  options{
    disableConcurrentBuilds() // 禁止多条流水线
    timestamps()
  }

stages{
  stage("打AB包"){
    steps{
            sh label:'打AB包',script:"${params.UNITY_PATH} -batchmode -nographics -projectPath ${params.PROJ_PATH} -logFile ${params.LOG_PATH} -executeMethod ${params.BUILD_AB}"
    }
  }

  stage("打包"){
      steps{
        sh label:'打包',script:"${params.UNITY_PATH} -batchmode -nographics -projectPath ${params.PROJ_PATH} -logFile ${params.LOG_PATH} -executeMethod ${params.RUN_FUN} -quit ${params.EXPORT_PATH}"
      }
    }  
  }
}

//"JenkinsBuilder.RunBuilds" "$BuildTarget""
//  stage('获取参数'){
//       steps{
//         sh label:' ',script:"echo ${params.str}"
//         sh label:' ',script:"echo ${params.bool}"
//         sh label:' ',script:"echo ${params.chs}"
//         sh label:' ',script:"echo ${params.text}"
//         sh label:' ',script:"echo ${foo}"
//       }
//     }
//     stage("修改资源"){
//       steps{
//         sh label:' ',script:' echo build'
//       }
//     }

//     stage("打 AB 包"){
//       steps{
//         sh label:' ',script:' echo build'
//       }
//     }

//     stage("导出工程"){
//       steps{
//         sh label:' ',script:' echo build'
//       }
//     }
//     stage('导出apk'){
//       steps{
//         sh label:' ',script:' echo build'
//       }
//     }
//     stage('上传'){
//         steps{
//           sh label:' ',script:" echo release"
//         }
//       }
//   }
