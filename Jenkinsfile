pipeline {
    agent any
    environment { 
        CC = 'clang'
    }
   
    parameters {
        choice(name: 'env', choices: ['test', 'dev'], description: '自动化运行环境')
        choice(name: 'range', choices: ['assign', 'all'], description: '自动化运行范围')
        string(name: 'project_name', defaultValue: '', description: '触发自动化运行的工程名')
        string(name: 'job_number', defaultValue: '', description: '触发自动化运行的流水线构建号')
    }
    
    stages {
        stage('Example') {
            when{
             environment name: 'CC', value: 'clang'
         }
         input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
         }
         
            steps {
               
                echo "${env.CC}"
                echo "${params.range}"
                
                echo "hello ${PERSON}"
                script{
                    if ("${params.env}"=='test')
                    {
                        echo "当前环境环境环境是环境是是 test"
                    }
                    else
                    {
                        echo "dang'qian当前huan'jing当前环境shi当前环境是 ${params.env}"
                        return
                    }
                    def browsers=["Chrome","Firefox"]
                    for(int i=0;i<browsers.size();++i){
                        echo "this is ${browsers[i]} browser"
                    
                    }
                }
            }
        }
    }
}
