@Grapes([
   @Grab('org.yaml:snakeyaml:1.17')
])

import org.yaml.snakeyaml.Yaml
//import org.yaml.snakeyaml.DumperOptions
//import static org.yaml.snakeyaml.DumperOptions.FlowStyle.BLOCK

node{
    //sh 'if cd trial; then git pull; else git clone https://github.com/RavikumarNagaraja/trial.git trial; fi'
    sh 'echo inside node'
    data = readYaml file: 'trial/IAM.yml'
}

pipeline {
    agent any
    stages{
        stage ('Build'){
            steps{
                sh 'echo hello world'
                sh 'if cd trial; then git pull; else git clone https://github.com/RavikumarNagaraja/trial.git trial; fi'
                sh 'python --version'
                sh 'python trial/trial.py'
                sh 'echo hello ravi'
                sh 'echo data[ravi]'
            }
        }
    }
    post{
        always{
            echo 'Always runs'
        }
        success{
            echo 'Runs on success'
        }
        failure{
            echo 'Runs on Failure'
        }
    }
    
}
