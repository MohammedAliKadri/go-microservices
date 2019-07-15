@Library("mak-dsl@test") _

def deployConfig = [
    deploy: [
        int: true,
        qa: false,
        stage: false,
        prod: false
    ],
    branch: "test"  
]


makci{
    civariables = deployConfig

}

