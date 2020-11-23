## Java Flight Recorder


Es una herramienta para capturar data de performance de bajo nivel.
Java Flight Recorder (JFR) es una herramienta de monitoreo que recopila información sobre los eventos 
en una máquina virtual Java (JVM) durante la ejecución de una aplicación Java. JFR es parte de la 
distribución JDK y está integrado en la JVM.


## JFR Compoenentes

### Eventos

* an instant event is logged immediately once it occurs
* a duration event is logged if its duration succeeds a specified threshold
* a sample event is used to sample the system activity

### Dataflow


Construcción de la imágen docker de los microservicios con argumentos:

Caso 1: Activar Flight Recorder (JFR) como argumento de partida de java.

Caso 2: Setear parámetros de memoria de JVM

 

El archivo de JRF debe quedar en el punto de montaje de los logs de los microservicios

## POC


1.- Generar una Aplicación Web Java de Spring Boot. O usar el ejemplo de Baeldung, O un ejemplo de BCH.
2.- Ejecutar con Flight Recorder
3.- Ejecutar con Flicght Recorder en docker con Entripoint
4.- Hacer que el entrypoint 






## Configuración de JAVA_HOME 

```
✘ rvaldes@MacBook-Pro-de-Rodrigo  ~/ms-demomonitor   feature/archetype-init  /usr/libexec/java_home -V
Matching Java Virtual Machines (5):
    14.0.1 (x86_64) "Oracle Corporation" - "OpenJDK 14.0.1" /Library/Java/JavaVirtualMachines/openjdk-14.0.1.jdk/Contents/Home
    11.0.9 (x86_64) "Oracle Corporation" - "Java SE 11.0.9" /Library/Java/JavaVirtualMachines/jdk-11.0.9.jdk/Contents/Home
    11.0.7 (x86_64) "AdoptOpenJDK" - "AdoptOpenJDK 11" /Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home
    1.8.271.09 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home
    1.8.0_251 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_251.jdk/Contents/Home
/Library/Java/JavaVirtualMachines/jdk-11.0.9.jdk/Contents/Home
 rvaldes@MacBook-Pro-de-Rodrigo  ~/ms-demomonitor   feature/archetype-init  export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.0.9.jdk/Contents/Home
```

java -XX:+UnlockCommercialFeatures -XX:+FlightRecorder -XX:StartFlightRecording=duration=60s,filename=myrecording.jfr -jar target/ms-demomonitor-0.0.1-SNAPSHOT.jar
java -XX:+UnlockCommercialFeatures -XX:+FlightRecorder -jar target/web-spring-demo-0.1.jar



## Publicar app en contenedor docker

```
docker build --tag web-app:1.0 .
docker run --publish 8000:18082 --detach --name web-app web-app:1.0
docker run --publish 8000:18082 --name web-app web-app:1.0
```

```
docker build --tag web-app-docker:1.0 .
docker run -ti f4775b438c36
docker run --publish 8000:18082 --name web-app web-app-docker:1.0
```



## Referencias
* [Baeldung - Monitoring Java Applications with Flight Recorder](https://www.baeldung.com/java-flight-recorder-monitoring)

* [JFR Runtime Guide](https://docs.oracle.com/javacomponents/jmc-5-4/jfr-runtime-guide/about.htm#JFRUH170)

* [Dzone - Using Java flight recorder] (https://dzone.com/articles/using-java-flight-recorder-with-openjdk-11-1)


java -XX:+UnlockCommercialFeatures -XX:+FlightRecorder -XX:StartFlightRecording=duration=60s,filename=myrecording.jfr -jar target/ms-demomonitor-0.0.1-SNAPSHOT.jar

-XX:FlightRecorderOptions=defaultrecording=true,dumponexit=true,dumponexitpath=path



ENTRYPOINT ["java","-XX:+FlightRecorder","-XX:StartFlightRecording=duration=120s,filename=/opt/artefactos/LOGS_APP_BANCO_IS_UNDEFINED/dsadasd.jfr","-XX:FlightRecorderOptions=defaultrecording=true,dumponexit=true,dumponexitpath=/opt/artefactos/LOGS_APP_BANCO_IS_UNDEFINED","-Djava.security.egd=file:/dev/./urandom","-Djava.net.preferIPv4Stack=true","-Dserver.port=8080","-jar","app.jar"]

-XX:FlightRecorderOptions=loglevel=debug


ENTRYPOINT ["java","-XX:+FlightRecorder","-XX:FlightRecorderOptions=loglevel=debug","-XX:StartFlightRecording=duration=120s,filename=/opt/artefactos/LOGS_APP_BANCO_IS_UNDEFINED/dsadasd.jfr","-XX:FlightRecorderOptions=defaultrecording=true,dumponexit=true,dumponexitpath=/opt/artefactos/LOGS_APP_BANCO_IS_UNDEFINED","-Djava.security.egd=file:/dev/./urandom","-Djava.net.preferIPv4Stack=true","-Dserver.port=8080","-jar","app.jar"]



https://mkyong.com/java/java-jcmd-not-found/