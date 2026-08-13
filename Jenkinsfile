pipeline {
    agent any
    
stages{
    stage("git checkout"){
        steps{
            git branch: 'master', 
            url: 'https://github.com/jagadish82/Granfana.git'
             }
        }

    stage("node-exporter"){
        steps{
            sh "docker run -d -p 9100:9100 --name node-exporter jagadish69/node-exporter"
            }
        }

    stage("prometheus"){
        steps{
            sh "docker run -d -p 9090:9090 --name prometheus -v /home/oracle/prometheus.yml:/etc/prometheus/prometheus.yml jagadish69/prometheus"
            }
        }

    stage("grafana"){
        steps{
            sh "docker run -d -p 3000:3000 --name grafana jagadish69/grafana"
            }
        }
    }
}
