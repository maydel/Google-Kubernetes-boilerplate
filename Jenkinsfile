pipeline {
    agent any

    stages {
        stage('Gitcheckout') {
            steps {
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/maydel/Google-Kubernetes-boilerplate.git'
            }
        }
    
        stage('currencyservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/currencyservice/'){
               sh "docker build -t maydel/currencyservice:latest . "
               sh "docker push maydel/currencyservice:latest "
               sh "docker rmi maydel/currencyservice:latest "
}
            } }  
        }
    }
    
    stage('loadgenerator') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/loadgenerator/'){
               sh "docker build -t maydel/loadgenerator:latest . "
               sh "docker push maydel/loadgenerator:latest "
               sh "docker rmi maydel/loadgenerator:latest "
}
            } }  
        }
    }

    stage('productcatalogservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/productcatalogservice/'){
               sh "docker build -t maydel/productcatalogservice:latest . "
               sh "docker push maydel/productcatalogservice:latest "
               sh "docker rmi maydel/productcatalogservice:latest "
}
            } }  
        }
    }
    
    stage('checkoutservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/checkoutservice/'){
               sh "docker build -t maydel/checkoutservice:latest . "
               sh "docker push maydel/checkoutservice:latest "
               sh "docker rmi maydel/checkoutservice:latest "
}
            } }  
        }
    }
    
    stage('shippingservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/shippingservice/'){
               sh "docker build -t maydel/shippingservice:latest . "
               sh "docker push maydel/shippingservice:latest "
               sh "docker rmi maydel/shippingservice:latest "
}
            } }  
        }
    }
    
    stage('cartservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/cartservice/src'){
               sh "docker build -t maydel/cartservice:latest . "
               sh "docker push maydel/cartservice:latest "
               sh "docker rmi maydel/cartservice:latest "
}
            } }  
        }
    }
    
    stage('emailservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/emailservice'){
               sh "docker build -t maydel/emailservice:latest . "
               sh "docker push maydel/emailservice:latest "
               sh "docker rmi maydel/emailservice:latest "
}
            } }  
        }
    }
    
    stage('paymentservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/paymentservice'){
               sh "docker build -t maydel/paymentservice:latest . "
               sh "docker push maydel/paymentservice:latest "
               sh "docker rmi maydel/paymentservice:latest "
}
            } }  
        }
    }
    
     stage('frontend') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/frontend'){
               sh "docker build -t maydel/frontend:latest . "
               sh "docker push maydel/frontend:latest "
               sh "docker rmi maydel/frontend:latest "
}
            } }  
        }
    }
    
    stage('recommendationservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/recommendationservice'){
               sh "docker build -t maydel/recommendationservice:latest . "
               sh "docker push maydel/recommendationservice:latest "
               sh "docker rmi maydel/recommendationservice:latest "
}
            } }  
        }
    }
    
    stage('adservice') {
            steps {
                script {
               withDockerRegistry(credentialsId: 'Docker', toolName: 'Docker') {
                   dir('/var/lib/jenkins/workspace/project/app/adservice'){
               sh "docker build -t maydel/adservice:latest . "
               sh "docker push maydel/adservice:latest "
               sh "docker rmi maydel/adservice:latest "
}
            } }  
        }
    }
        stage('deploy to kubernetes') {
            steps {
                script {
               withKubeConfig(caCertificate: '', clusterName: 'project1', contextName: '', credentialsId: 'Kubernetes', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://CEB0D8E321AF85F209B8F92FE240829D.gr7.ca-central-1.eks.amazonaws.com') {
                  sh "kubectl apply -f kubernetes-manifests.yaml"
}
    }
}
}
}
}
