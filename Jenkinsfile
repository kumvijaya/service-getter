
node {
    String confUrl = 'https://confluence.com'
    String appName = 'RMI-XXXXXX'
    stage('Get Services Info') {
        checkout scm
        withCredentials([usernamePassword(credentialsId: 'CONFLUENCE', usernameVariable: 'CONFLUENCE_USER', passwordVariable: 'CONFLUENCE_TOKEN')]) {
            String serviceInfoCommand = """
                python -m pip install -r requirements.txt --user
                python service-getter.py -u ${confUrl} -a ${appName}
            """
            def output = sh(returnStdout: true, script: serviceInfoCommand)
            print(output)
        }
    }
}