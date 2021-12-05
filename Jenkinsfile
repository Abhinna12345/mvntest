pipeline {
 agent { docker { image 'maven:3.3.3' } }
	 stage('Git Checkout'){
		git 'https://github.com/Abhinna12345/mvntest'  
	 }
	 stage('Maven Package'){
		sh 'mvn clean package'
		sh 'mv target/mvntest*.war target/mvntest.war'
	 }
}
