def imageName=ta2199/demo-jenkins

node('workers'){
    stage('Checkout'){
        checkout scm
    }
    stage('Unit Test'){
        sh "docker build -t ${imageName} -f Dockerfile.test ."
        sh "docker run --rm ${imageName} "
    }
}
