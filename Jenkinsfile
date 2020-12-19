
node  {

    stage('SCM Checkout')
    {
     git credentialsId: 'suneel@35C', url: 'https://github.com/suneel35/phpmysql-app.git'   
    }
    
    stage('Run Docker Compose File')
    {
        sh 'sudo docker-compose build'
        sh 'sudo docker-compose up -d'
    }
  stage('PUSH image to Docker Hub')
    {
   /* withCredentials([usernameColonPassword(credentialsId: 'DockerHUB', variable: 'DHPWD')]) 
   {
                   sh "docker login -u suneel35 -p ${DHPWD}"
				   }
				   sh 'docker push suneel35/phpmysql_app'
				   */
				   // docker.withRegistry('https://registry.hub.docker.com', 'DockerHUB' ) 
				   {
				   sh 'sudo docker login -u "suneel35" -p "suneel@35C" docker.io'
				   //sh 'sudo docker push suneel35/mysql'
				   //sh 'sudo docker push suneel35/job1_web1.0'
             sh 'sudo docker push suneel35/job1_web2.0'
            // sh 'docker push suneel35/mysql' 
	}     
    }
