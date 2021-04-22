pipeline{
    agent any
    parameters{
        password(name: "Username", default: 'SECRET')
        password(name: "Password", default: 'SECRET')

    }
    stages{
        stage("Build Front-end"){
            steps{
                sh 'docker build -t test .' 
            }
        }

        stage("Deploy to Docker Hub"){
            sh 'docker login --username="${Username}" --password="${Password}"'
            sh 'docker push test'
        }

    }

}