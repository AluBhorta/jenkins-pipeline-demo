# Jenkins Pipeline Demo



## Usage

Start jenkins instance in a container with persistent volume
```bash
sudo docker run --name myjenkins -p 8080:8080 -p 50000:50000 -v `$JENKINS_HOME`:/var/jenkins_home jenkins/jenkins:alpine
```

## Res

- Jenkins [getting started](https://jenkins.io/doc/pipeline/tour/getting-started) Doc
- [Old Docker hub image](https://hub.docker.com/_/jenkins?tab=description) for Jenkins

