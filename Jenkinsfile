node {
   
   
    
    // Clone sample git repo
    stage('clone sources') {
    git url: 'https://github.com/leereilly/hello-world-java.git'
    }
    
    stage('Compile hello world java pro') {
        sh 'javac  HelloWorld.java'
    }
    
    stage ('Run Hello-World java program') {
       sh  'java HelloWorld'
    }
    
    
    
    if (env.BRANCH_NAME == 'master') {
                echo 'I only execute on the master branch'
            } else {
                echo 'I execute elsewhere'
            }
            
    
    stage ('SelectBranch') {
    env.BRANCH_NAME = input(
    id: 'BRANCH_NAME', message: 'Which Branch to\'s Build?', parameters: [
    [$class: 'TextParameterDefinition', defaultValue: 'master', description: 'Environment', name: 'env']
    ])
    echo ("Env: "+BRANCH_NAME)        
    }
    
    if (env.BRANCH_NAME == 'master') {
                echo 'I only execute on the master branch'
            } else {
                echo 'I execute elsewhere'
            }
            
           
    
}
