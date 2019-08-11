pipeline {
	agent any
	stages {
		stage('Upload to AWS') {
			steps {
				sh 'echo "Running Jenkins upload..."'
				sh 'tidy -q -e *.html'
				withAWS(region:'us-west-2', credentials:'aws-static') {
    				s3Upload(file:'index.html', bucket:'pmbrull-udacity-jenkins', path:'index.html')
				}
			}
		}
	}
}
