#!/usr/bin/env groovy

pipeline {
    agent any
    environment {
        BRANCH_PATTERN= '*'
    }
    
    
        parameters {
            choice(
                name: 'BUILD_TYPE',
                choices:"nightly\nsnapshots\nrc",
                description: "Build Type")
            
            //string(name: 'BRANCH_TO_BE_BUILT', defaultValue: '${SE_DEFAULT_BRANCH}', description: 'Branch To Be Built')
            //string(name: 'UI_VERSION', defaultValue: '${SE_DEFAULT_BRANCH}')
            booleanParam(name: 'FULL_BUILD', defaultValue: false)
            booleanParam(name: 'PATCH_BUILD', defaultValue: true)
            choice(name: 'WLS_VERSION', choices: ['12.2.1.2.0', '12.1.3'], description: 'WLS Client Version')
            
            
    }
    stages {
        stage("build") {
            steps {
                //echo "Working"
                echo "Hello ${params.BUILD_TYPE}"
                echo "Global ${SE_DEFAULT_BRANCH}"
                echo "Global ${SE_DEFAULT_BRANCH}"
                echo "Global ${SE_DEFAULT_BRANCH}"
                choice(name: 'WLS_VERSION', choices: ['12.2.1.2.0', '12.1.3'], description: 'WLS Client Version')
            }
        }
        
        stage("Clone UI Branch") {
        steps {
         echo "Cloning UI Branch"   
            
        }
        
    }
        
        
        //*------------------------------
        
        
        stage ('Prepare') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: "origin/${BRANCH_PATTERN}"]],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'LocalBranch']],
                    submoduleCfg: [],
                    userRemoteConfigs: [[
                        credentialsId: 'bmangesh',
                        url: 'https://github.com/bmangesh/JenkinsPipeline']]])
            }
        }

        
            //*-------------------------------
        
        stage("Run Script") {
        steps {
         sh 'runScript.sh'  
            
        }
        
    }
    }
    
    
    
    
    
    
    
       
    
}
