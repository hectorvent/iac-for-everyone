# Preparar ambiente 

### Preparar Ambiente:

- Tener una cuenta de Digital Ocean. Si no la tienes, puedes registrarte [aqui](https://m.do.co/c/823262eb863f) y tener un bono de $200 por 60 días
- Instalar [SDKMAN](https://sdkman.io/install) (Si aun no tienes Java/Maven en tu maquina)
- Instalar con sdk java y maven
```shell
sdk install java 21.0.3-tem
sdk install maven 3.9.4
```
- Instalar Docker https://docs.docker.com/engine/install/ 
- Bajar imagen docker 
```shell
docker image pull hectorvent/iac-for-everyone
```
- Instalar [pulumi](Installar Pulumi https://www.pulumi.com/docs/install/)

### Validar ambiente

```shell
➜ docker --version
Docker version 26.1.4, build 5650f9b
```

```shell
➜ mvn --version   
Apache Maven 3.9.4 (dfbb324ad4a7c8fb0bf182e6d91b0ae20e3d2dd9)
Maven home: /Users/hectorvent/.sdkman/candidates/maven/current
Java version: 21.0.3, vendor: Eclipse Adoptium, runtime: /Users/hectorvent/.sdkman/candidates/java/21.0.3-tem
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "14.5", arch: "aarch64", family: "mac"
```

```shell
➜ java -version
openjdk version "21.0.3" 2024-04-16 LTS
OpenJDK Runtime Environment Temurin-21.0.3+9 (build 21.0.3+9-LTS)
OpenJDK 64-Bit Server VM Temurin-21.0.3+9 (build 21.0.3+9-LTS, mixed mode)
```