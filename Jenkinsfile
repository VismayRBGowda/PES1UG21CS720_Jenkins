pipeline {
agent any
stages {
stage('Clone repository') {
steps {
script {
checkout([$class: 'GitSCM',
branches: [[name: 'main']],
userRemoteConfigs: [[url:
'https://github.com/VismayRBGowda/PES1UG21CS720_Jenkins.git']],
])
}
}
}
stage('Build') {
steps {
script {
sh 'g++ Jenkins_lab-main/main/hello.cpp -o output'
}
}
}
stage('Test') {
steps {
script {
sh './output'
}
}
}
stage('Deploy') {
steps {
script {
echo 'Deployment step'
}
}
}
}
post {
failure {
echo 'Pipeline failed'
}
}
}
