pipeline{
    agent any
    parameters{
        password(name: "Username", defaultValue: 'SECRET')
        password(name: "Password", defaultValue: 'SECRET')

    }
    stages{
        stage("Build Front-end"){
            steps{
                sh 'docker build -t "${Username}"/realworld_frontend .' 
            }
        }

        stage("Deploy"){
            steps{
                sh 'docker login --username="${Username}" --password="${Password}"'
                sh 'docker push "${Username}"/realworld_frontend' 
            }
        }

    }

}