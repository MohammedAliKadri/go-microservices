@Library("mak-dsl@test") _

def ciConfig = [
  GoVersion: "1.11.4",
  CgoEnabled:"0"
]

def cdConfig = [
  env: [
    int: false,
    qa: false,
    stage: false,
    prod: false
  ],
  branch: "test",
]

makci{
    ci = ciConfig
    cd = [
        configValues: appConfig,
        deployStrategy: cdConfig
    ]
}
