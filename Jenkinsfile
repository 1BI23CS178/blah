pipeline {
agent any
tools {
maven 'Maven'
jdk 'jdk'

}
stages {
stage('Checkout') {
steps {
git branch: ‘master’, url: 'https://github.com/1BI23CS178/blah.git'
}
}
stage('Build') {
steps {
sh 'mvn clean package'
}
}
stage('Test') {
steps {
sh 'mvn test'
}
}
stage('Run Application') {
steps {
// Start the JAR application
sh 'java -jar target/myapp09.0-SNAPSHOT.jar'
}
}
}
post {
success {
echo 'Build and deployment successful!'
}

failure {
echo 'Build failed!'
}
}
}
