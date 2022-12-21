# Cómo desarrollabamos software hace 20 años



Metodologías: Waterfall (en cascada: Espiral, V)

Se definian una serie de ETAPAS (FASES) por las que el proyecto iba avanzando.
Cuándo acababamos un proyecto en fecha? NUNCA !

    TOMA DE REQUISITOS (día 1)
        ANALISIS / DISEÑO / PLAN        (diagramas de gantt)
            DESARROLLO
                PRUEBAS
                    DESPLIEGUE 
                        MNTO

    Plan:
        Hito 1  -   Fecha 10-Enero ---> 20 Enero
            Funcionalidad 1 \
            Funcionalidad 2  > Lo importante
            Funcionalidad 3 /
        Hito 2  -   Fecha 25-Febrero
        Hito 3
    
    Medida principal de progreso:
        - Forma más tradicional:    Le pregunto al desarrollador! Los desarrolladores (con buen ánimo)
                                    mentimos más que hablamos... pero a nosotros mismos
        - Formas creativas:         Número de lineas de código escritas por día/semana

    ¿Cuántas veces probaba el sistema? UNA AL FINAL
    ¿Cuántas veces instalaba el sistema? UNA AL FINAL

# Cómo desarrollamos hoy en día

Metodologías ágiles: SCRUM, XTREME PROGRAMMING (TDD, BDD, ATDD)
Se basan en el MANIFIESTO AGIL ! https://agilemanifesto.org/

> El software funcionando es la medida principal de progreso.
                VVVVVVV
                PROBADO por un tercero que sepa de pruebas! en un entorno limpio
    Para saber cómo va el proyecto voy a mirar el número de pruebas satisfechas en una unidad de tiempo!

> La simplicidad, o el arte de maximizar la cantidad de trabajo no realizado, es esencial.
    

> Nuestra mayor prioridad es satisfacer al cliente mediante la entrega temprana y continua de software
con valor.

> Entregamos software funcional frecuentemente, entre dos semanas y dos meses, con preferencia al periodo de
tiempo más corto posible.

SCRUM : Sprint

Sprint 1   -   Fecha 10-Enero  ** LO IMPORTANTE **
            Funcionalidad 1 √
            Funcionalidad 2 √
            Funcionalidad 3 x -> Se deja para el siguiente sprint

Se basan en entregas continuas incrementales del producto
    
    2 semanas ENTREGA 1 en producción       10% de la funcionalidad (100% funcional)
                                            + PRUEBAS 10%
                                            + Instalación
    2 semanas ENTREGA 2 en producción       5% de la funcionalidad (100% funcional)
                                            + PRUEBAS 15%
                                            + Instalación
                                            ...
                                           100%

    AUTOMATIZAR !

# DEV=>OPS 

cultura, filosofía, movimiento en pro de la AUTOMATIZACION
    
                Automatizables?     Herramientas                                Quién
PLAN                    x
CODE                    x
BUILD                   √           maven gradle sbt nuget msbuild dotnet       Desarrollo
TEST                    
    diseño              x
    ejecución           √           selenium appium karate postman cucumber     Tester + Desarrollo + Sistemas
                                    jmeter loadrunner soapui postman sonarqube
    Ese entorno de pruebas existe de antemano?  Puede ser... tradicionamente exisitía. 
                                                La tendencia es a que no exista. Quiero entornos de USAR Y TIRAR
                                                Contenedores
                                                Clouds. 
                                    Docker, Ansible, Terraform, Vagrant,        Sysadmin
                                    Puppet, Kubernetes, Openshift
------------------------------------------------------------------------ INTEGRACION CONTINUA
RELEASE                 √
------------------------------------------------------------------------ ENTREGA CONTINUA       C.D.elivery
DEPLOYMENT              √
------------------------------------------------------------------------ DESPLIEGUE CONTINUA    C.D.eployment
OPERATION               √           KUBERNETES (OPENSHIFT, TAMZU)
MONITOR                 √

Me falta por automatizar la llamada a todas esas automatizaciones: SERVIDORES DE AUTOMATIZACION
    JENKINS, BAMBOO, TEAMCITY, AZURE DEVOPS (TFS), TRAVISCI, Github actions, Gitlab CI/CD
    
    Pipeline (script)

## Tipos de pruebas de software

- Estáticas                             Prueba que no necesita poner un sistema en funcionamiento / ejecución para realizarse
    - Revisión de calidad de código     SONARQUBE
    - Revisión de requisitos
    - Revisión de un modelo de datos
- Dinámicas         Prueba que SI necesita poner un sistema en funcionamiento / ejecución para realizarse
    - Funcionales
        - Unitarias                     JUNIT           Desarrollo
        - Integración                   JUNIT
        - Sistema
    - No funcionales
        - Rendimiento
        - Estres
        - Carga
        - UI
        - HA
---
Unitarias           Se efectúa sobre un componente aislado de la aplicación
Integración         Prueba la COMUNICACION entre componentes
Sistema /End2End    Probamos el COMPORTAMIENTO DEL SISTEMA
    Aceptación      Son las que el cliente o yo requiero


# Sonarqube

Un analizador de código de programación principalmente.
- Y aporta sugerencias de mejora
- Identificar bugs, vulnerabilidades...
- Calificar el código... y en base a esa calificación, OTROS podrán decidir si 
  el código es apto o no para ir a producción

# Pruebas de software









