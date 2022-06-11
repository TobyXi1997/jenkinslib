pipeline{
	agent any
	options {
		timestamps()	//日志会有时间
		skipDefaultCheckout()  // 删除隐式 checkout scm  语句   主要作用是检查代码库
		disableConcurrentBuilds()  //禁止并行	并行项目 和分并行项目
		timeout(time：100,unit: HOURS)  //流水线超时设置1h
	}
	
	stages{		// 多个或者一个阶段
		stage('阶段名称'){
			steps{ // 步骤
				timeout(time:5, unit: "MINUTES"){   //步骤超时时间
					script{	// 填写运行代码
						println('获取代码')
					}
				}
			
			}
		}
		
	}	
	
	post{
		always{	//总是执行脚本片段
			script{
				println("always")
			
			}
		}
		
		success {	//成功后执行
			script{
				currentBuild.description = "\n 构建成功"
			}
		}
		
		failure{	// 失败后执行
			script{
				currentBuild.description = "\n 构建失败"
			}		
		}
		
		aborted{	// 取消后执行
			script{
				currentBuild.description = "\n 构建取消"
			}		
		}
	
	}
}
