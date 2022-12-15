# Configurar parametros adecuados para elasticsearch (que se usa dentro de sonar)

$ sudo su -
$ sysctl -w vm.max_map_count=262144
$ echo vm.max_map_count=262144 > /etc/sysctl.conf
$ exit

# Arrancamos la bbdd y sonar mediante docker-compose

$ docker-compose up (en la carpeta donde tenemos el fichero docker-compose.yaml)


# JAVA

Lenguajes compilados / interpretados

                                   javac                    java 
Programa (lenguaje JAVA) .java -> compila -> .class -> interpretan JVM -> binario ejecutable
                                            bytecode

# Alternativas a la sintaxis de JAVA:
- Kotlin
- Scala

## MAVEN, GRADLE

Maven es un programa de Apache  que ayuda:
- Crear un proyecto desde una plantilla (arquetipos)
- En el día de un proyecto JAVA: compilarlo, ejecutar pruebas unitarias, empaquetar, distribuirlo
- Gestión de dependencias
- Y otros menesteres: Mandar nuestro codigo a SonarQube

## Crear proyecto desde arquetipo con maven:
mvn archetype:generate \
    -DgroupId=curso.es \
    -DartifactId=mi-aplicacion \
    -DarchetypeArtifactId=maven-archetype-quickstart \
    -DarchetypeVersion=1.4 \
    -DinteractiveMode=false

Sistema de control de versión       CVS

Sistema de contol de código fuente  SCM