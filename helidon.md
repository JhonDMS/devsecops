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
/usr/libexec/java_home -V
mvn package
java -jar target/helidon-quickstart-se.jar
```



/usr/libexec/java_home -V
Matching Java Virtual Machines (4):
    14.0.1 (x86_64) "Oracle Corporation" - "OpenJDK 14.0.1" /Library/Java/JavaVirtualMachines/openjdk-14.0.1.jdk/Contents/Home
    11.0.7 (x86_64) "AdoptOpenJDK" - "AdoptOpenJDK 11" /Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home
    1.8.271.09 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home
    1.8.0_251 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_251.jdk/Contents/Home

 export JAVA_HOME=`/usr/libexec/java_home -v 11.0.7`



 export JAVA_HOME=`/usr/libexec/java_home -v 11.0.7`


 export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home