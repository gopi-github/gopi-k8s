pipeline {
    agent any
	stages{
		stage('Build Docker Image'){
            		steps{
                		sh "docker build . -t v1"
            }
        }
		stage('Push Image to Dockerhub'){
			steps{
				withCredentials([string(credentialsId: 'dockerhubpwd', variable: 'dockerhubpwd')]) {
				sh "docker login -u selgo001 -p ${dockerhubpwd}"
				sh "docker push v1"
		}

}
}
}
}
