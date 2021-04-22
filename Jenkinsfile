pipeline{
    agent any
    parameters{
        password(name: "Username", defaultValue: 'SECRET')
        password(name: "Password", defaultValue: 'SECRET')

    }
    stages{
        stage("Build Front-end"){
            steps{
                sh 'docker build -t test .' 
            }
        }

        stage("Deploy"){
            steps{
                sh 'docker login --username="${Username}" --password="${Password}"'
                sh 'docker push test' 
            }
        }

    }

}