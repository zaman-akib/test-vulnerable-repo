pipeline {
    agent any
    stages {
        stage("unit-test") {
            steps {
                echo 'UNIT TEST EXECUTION STARTED'
            }
        }
        stage("functional-test") {
            steps {
                echo 'FUNCTIONAL TEST EXECUTION STARTED'
            }
        }
        
       stage("synopsys-security-scan") {
            steps {
                echo 'SYNOPSYS SECURITY SCAN EXECUTION STARTED'
                synopsys_scan synopsys_security_platform: 'blackduck', bridge_blackduck_url: "${env.BLACKDUCK_URL}", bridge_blackduck_api_token: "${env.BLACKDUCK_TOKEN}",
                bridge_polaris_application_name: "test_jenkins", bridge_polaris_project_name: "springboot-pipeline-test", bridge_polaris_assessment_types: "SCA"
            }
        }
         /*stage("synopsys-detect-scan") {
            steps {
                echo 'SYNOPSYS DETECT SCAN EXECUTION STARTED'
                synopsys_detect detectProperties: "--blackduck.api.url=https://testing.blackduck.synopsys.com/ --blackduck.api.token=MDQxNjNjMTAtMGY4NS00YmMzLTgyOTMtYmM5ZTYwM2E5NTY1OjkzYmExMThiLTdmOTctNDk4ZS04ZGU0LTNhNmJlYmM0MWM5OA== --blackduck.trust.cert=true --detect.tools=DETECTOR --detect.cleanup=false --blackduck.offline.mode=true"
            }
        }*/
        stage("build") {
            steps {
                echo 'BUILD EXECUTION STARTED'
                echo 'Pulling...' + env.BRANCH_NAME
            }
        }
    }
}
