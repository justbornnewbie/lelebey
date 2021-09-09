def git_url = 'https://github.com/rjmsas/lelebey.git'
def git_branch = 'main'

pipeline
{
    agent
    {
        label 'worker1'
    }

    stages
    {
        stage('build')
        {
            
            steps{
                   sh '''
                   cd haproxy
                   mkdir -p /opt/docker/haproxy
                   cp haproxy.cfg /opt/docker/haproxy
                   cp haproxy-compose.yml /opt/docker/haproxy
                   '''
               }
        
        }
        stage('start-haproxy')
        {
            
            steps{
                   sh '''
                   cd haproxy              
                   docker-compose -f haproxy-compose.yml down | exit 0
                   docker-compose -f haproxy-compose.yml up -d
                   '''
               }
        
        }
    }
}