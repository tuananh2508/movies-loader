def imageName = 'ta2199/demo-jenkins'

node('workers'){
    stage('Checkout'){
        checkout scm
    }
    
    stage('Unit Tests'){
        docker.withRegistry('', '8266d0f0-bf5a-495c-bdbf-896e4f36e65c') {
            def imageTest= docker.build("${imageName}-test", "-f Dockerfile.test .")
            imageTest.inside{
                sh 'python test_main.py'
            }
        }
    }
}
