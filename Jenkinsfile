node {

  
    stage('Checkout'){
        git branch: 'main',
            credentialsId: 'git',
            url: 'https://github.com/medXPS/monolithic_e-Banking_configMaps_statefulsets.git'
    }



    stage('Deploy') {
     
        step([$class: 'KubernetesEngineBuilder',
            projectId: env.PROJECT_ID,
            clusterName: env.CLUSTER,
            location: env.REGION,
            manifestPattern: 'K8s/',
            credentialsId:env.PROJECT_ID,
            verifyDeployments: true

        ])
    }
}


