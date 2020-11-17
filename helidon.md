# Helidon Java Microservice Framework

* [Helidon Project](https://helidon.io/#/)

"Lightweight.Fast.Crafted for Microservices"

## Descripción

Helidon es una colección de librerías Java para escribir microservicios 
que se ejecutan en un core web rápido basado en [Netty](https://netty.io/).



## Generación de proyecto a partir de un archetipo Maven

````
mvn -U archetype:generate -DinteractiveMode=false \
    -DarchetypeGroupId=io.helidon.archetypes \
    -DarchetypeArtifactId=helidon-quickstart-se \
    -DarchetypeVersion=2.1.0 \
    -DgroupId=io.helidon.examples \
    -DartifactId=helidon-quickstart-se \
    -Dpackage=io.helidon.examples.quickstart.se

cd helidon-quickstart-se
mvn package
```