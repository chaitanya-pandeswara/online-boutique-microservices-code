pipeline {
    agent any
    
    environment {
    DOCKERHUB_CREDENTIALS = credentials('docker-chaitu')
    }
    
    stages {
        
        stage('Git Checkout') {
            steps {
                git branch: 'feature/SCRUM-51-Make-it-Local-Like-we-developed-it', credentialsId: 'github-chaitanya-pandeswara', url: 'https://github.com/chaitanya-pandeswara/online-boutique-microservices-code.git'
            }
        }

        stage('Docker Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        
        stage('Adservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/adservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:adservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:adservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o adservice-report.html chaitu685/online-boutique:adservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:adservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "adservice-report.html",
                    reportName: "Trivy Adservice Report",
                ])
            }
        }

        stage('Cartservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/cartservice/src') {
                        
                        sh 'docker build -t chaitu685/online-boutique:cartservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:cartservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o cartservice-report.html chaitu685/online-boutique:cartservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:cartservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "cartservice-report.html",
                    reportName: "Trivy Cartservice Report",
                ])
            }
        }

        stage('Checkoutservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/checkoutservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:checkoutservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:checkoutservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o checkoutservice-report.html chaitu685/online-boutique:checkoutservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:checkoutservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "checkoutservice-report.html",
                    reportName: "Trivy Checkoutservice Report",
                ])
            }
        }

        stage('Currencyservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/currencyservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:currencyservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:currencyservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o currencyservice-report.html chaitu685/online-boutique:currencyservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:currencyservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "currencyservice-report.html",
                    reportName: "Trivy Currencyservice Report",
                ])
            }
        }

        stage('Emailservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/emailservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:emailservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:emailservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o emailservice-report.html chaitu685/online-boutique:emailservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:emailservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "emailservice-report.html",
                    reportName: "Trivy Emailservice Report",
                ])
            }
        }

        stage('Frontend Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/frontend') {
                        
                        sh 'docker build -t chaitu685/online-boutique:frontend-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:frontend-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o frontend-report.html chaitu685/online-boutique:frontend-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:frontend-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "frontend-report.html",
                    reportName: "Trivy Frontend Report",
                ])
            }
        }

        stage('Loadgenerator Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/loadgenerator') {
                        
                        sh 'docker build -t chaitu685/online-boutique:loadgenerator-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:loadgenerator-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o loadgenerator-report.html chaitu685/online-boutique:loadgenerator-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:loadgenerator-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "loadgenerator-report.html",
                    reportName: "Trivy Loadgenerator Report",
                ])
            }
        }

        stage('Paymentservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/paymentservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:paymentservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:paymentservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o paymentservice-report.html chaitu685/online-boutique:paymentservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:paymentservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "paymentservice-report.html",
                    reportName: "Trivy Paymentservice Report",
                ])
            }
        }

        stage('Productcatalogservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/productcatalogservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:productcatalogservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:productcatalogservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o productcatalogservice-report.html chaitu685/online-boutique:productcatalogservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:productcatalogservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "productcatalogservice-report.html",
                    reportName: "Trivy Productcatalogservice Report",
                ])
            }
        }

        stage('Recommendationservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/recommendationservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:recommendationservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:recommendationservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o recommendationservice-report.html chaitu685/online-boutique:recommendationservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:recommendationservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "recommendationservice-report.html",
                    reportName: "Trivy Recommendationservice Report",
                ])
            }
        }

        stage('Shippingservice Docker Build-Tag-Scan-Push') {
            steps {
                script {
                    dir('src/shippingservice') {
                        
                        sh 'docker build -t chaitu685/online-boutique:shippingservice-${BUILD_NUMBER}.0 .'
                    }    
                        
                       // Below line is to fail the stage if vulnerabilities found are HIGH and CRITICAL
                       // sh 'trivy image chaitu685/online-boutique:shippingservice-${BUILD_NUMBER}.0 --exit-code 1 --severity HIGH,CRITICAL --timeout 15m'
                       
                       sh """
                       trivy image --format template --template "@/usr/bin/html.tpl" -o shippingservice-report.html chaitu685/online-boutique:shippingservice-${BUILD_NUMBER}.0 --timeout 15m
                       """
                        
                       sh 'docker push chaitu685/online-boutique:shippingservice-${BUILD_NUMBER}.0'
                }
            
                publishHTML(target: [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: ".",
                    reportFiles: "shippingservice-report.html",
                    reportName: "Trivy Shippingservice Report",
                ])
            }
        }
        
        stage('Docker Images Cleanup') {
            steps {
                sh 'docker rmi $(docker images -a -q)'
            }
        }
        
        stage('Docker Logout') {
            steps {
                sh 'docker logout'
            }
        }
    }
}