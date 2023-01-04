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
	    	checkout([$class: 'GitSCM', branches: [[name: '${tag}']], extensions: [], userRemoteConfigs: [[credentialsId: 'd1c2b682-5736-4dab-a41f-d75892d26e05', url: 'https://github.com/diony-chen/test.git']]])
	    }
        }
	
	stage('通过maven构建项目') {
            steps {
		sh '/home/docker/jenkins_docker/data/maven/bin/mvn clean package -DskipTests'
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
