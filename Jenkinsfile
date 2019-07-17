
@Library("mak-dsl@test") _

def ciConfig = [
  GoVersion: "1.11.4",
  CgoEnabled:"0",
  GoOs: "linux",
  GoArch: "amd64",
  LdFlags: [
    BuildVersion: "-X github.com/ContinuumLLC/platform-remote-access-service/src/web.BuildNumber",
    BuildCommit: "-X github.com/ContinuumLLC/platform-remote-access-service/src/web.BuildCommitSHA"
    ],
  TestPackages: ["./dal", "./service", "./service/config", "./web"],
  Version: "1.0.0"
]

def appConfig = [
    int: [ 
      LogLevel: "INFO",
      ThirdPartyIntegrationURL: "http://thirdparty.int.kube.itsupport247.net/third-party-integration/v1",
      BaseEntitlementURL: "http://entitlement.int.kube.itsupport247.net/entitlement/v1/mgmt/",
      BaseITSApiURL:  "http://rmmitsapi.dtitsupport247.net/rmmitsapi/v1/",
      BaseAssetMSURL: "http://asset.int.kube.itsupport247.net/asset/v1/",
      BaseAgentMSURL: "https://agent.exec.itsupport247.net/agent/v1/",
	    CassandraHosts: "commoncassandra.int.kube.itsupport247.net:9042",
	    KafkaHosts: "kafka.int.kube.itsupport247.net:9092",
      Cassandra: [cmsservice: "common", migration: "false", keyspace: "remote_access_db"]
    ],

    qa: [ 
      LogLevel: "INFO",
      ThirdPartyIntegrationURL: "http://internal-third-party-integration-elb-1263876329.ap-south-1.elb.amazonaws.com/third-party-integration/v1/",
      BaseEntitlementURL: "http://internal-entitlement-partnerspecific-72155629.ap-south-1.elb.amazonaws.com/entitlement/v1/mgmt/",
      Cassandra: [cmsservice: "common", migration: "false", keyspace: "remote_access_db"]
    ]
]

def cdConfig  = [
    env: [
        int: true,
        qa: false,
        stage: false,
        prod: false
    ],
    branch: "test"  
]


makjuno{
    ci = ciConfig
    cd = [ 
        deployStratergy: cdConfig,           
        configValues:  appConfig   
    ]  
}

