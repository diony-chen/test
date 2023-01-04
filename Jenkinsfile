// 所有的脚本命令都放在pipeline中
pipeline {
	// 指定任务在哪个集群节点中执行
    agent any

	// 声明全局变量， 方便后面使用
	environment {
		key = 'value'
	}
	
    stages {
        stage('拉取Git仓库代码') {
            steps {
                echo '拉取Git仓库代码 - SUCCESS'
            }
        }
		stage('通过maven构建项目') {
            steps {
                echo '通过maven构建项目 - SUCCESS'
            }
        }
		stage('通过Docker制作自定义镜像') {
            steps {
                echo '通过Docker制作自定义镜像 - SUCCESS'
            }
        }
		stage('通过Publish Over SHH通知目标服务器') {
            steps {
                echo '通过Publish Over SHH通知目标服务器 - SUCCESS'
            }
        }
    }
}
