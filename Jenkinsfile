node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("bharathjg/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
    def Azkey=credentials('Azkey')
    def Azname=credentials('Azname')
    bat 'az storage blob upload-batch --account-key $Azkey --account-name $Azname -d newapp -s D:\\web_app'
}
