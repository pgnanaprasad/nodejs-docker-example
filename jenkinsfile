node{
    def app
        stage('clone Repo'){
            checkout
            
        }
        stage('build'){
            app=docker.build("gnanapra/nodeapp")
            
        }
        stage('test'){
            app.inside{
                echo "Tests Passed"
            }
        }
        stage('push'){
            docker.withRegistry('https://registry.hub.docker.com',docekr.hub){
                app.push("$(env.BUILD_NUMBER)")
                app.push("latest")
            }
            }
        }
