pipeline{
   
    agent {label 'linagent2'}
	options {
    skipDefaultCheckout()
  }
    
    stages{
        stage('build'){
        steps{
            sh 'echo hello'
                    		
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 image add docker.io/debian:latest'
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 image wait docker.io/debian:latest'
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 image get docker.io/debian:latest'
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 system feeds list'
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 image vuln docker.io/debian:latest os'
			sh 'anchore-cli --u admin --p foobar --url http://localhost:8228/v1 evaluate check docker.io/debian:latest'
            
        }
        }
    }
}
