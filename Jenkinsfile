def foo() {
    echo "foo"
}

def boo(String txt = "default value") {
    echo txt
}

def loop() {
    array = ["one", "two", "three"]
    for(String item : array) {
        echo item
    }
}

pipeline {
    agent any

    stages{
        stage("one"){
            steps{
                foo()

                library identifier: 'hello@master', retriever: modernSCM([$class: 'GitSCMSource', credentialsId: '', id: 'db6e273a-26b3-4c87-a8f8-61adfedbca2f', remote: 'https://github.com/LinuxSuRen/share-pipeline', traits: [[$class: 'jenkins.plugins.git.traits.BranchDiscoveryTrait']]])
            }
        }
        stage("two"){
            steps{
                script{
                    suren.hello('world')
                }
            }
        }
    }
}