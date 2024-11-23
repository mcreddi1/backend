pipeline{
    agent{
        label 'agent-1'
    }
    options{
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        //retry(1)
    }
    environment{
        DEBUG = 'TRUE'
        appVersion = ''    //this will become global var and we can use across pipeline
    }
    stages{
        stage("Read the Version"){
            steps{
                script{
                def packageJson = readJSON file: 'package.json'
                appVersion = packageJson.version
                echo 'App Version: ${appVersion}'
                }
            }
        }
    }
}