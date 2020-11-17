# Bamboo CI/CD

## 

* [Docker Hub - Atlassian Bamboo](https://hub.docker.com/r/atlassian/bamboo-server)


```
docker volume create --name bambooVolume
docker run -v bambooVolume:/var/atlassian/application-data/bamboo --name="bamboo" --init -d -p 54663:54663 -p 8085:8085 atlassian/bamboo-server
```



