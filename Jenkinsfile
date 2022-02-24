pipeline {
   agent any
   environment {
	PATH="/opt/maven-3.8.4/bin:$PATH"
}
     stages {
	stage('gitcode cloning') {
		steps {
		   git credentialsId: 'github-server-credentials', url: 'https://github.com/chiranjeevi36/hello-world.git'
}
}
	stage('build code') {
	     steps {
		sh "mvn clean install"
}
}
}
}
