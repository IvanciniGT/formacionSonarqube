

Dos
Denegación de servicio
- Miles de peticiones a un servidor web -> OFFLINE
- 200 peticiones que tardan en resolverse 10 horas
    - Mande en la coenxión un bit por segundo 
    - Peticiones muy pesadas

Testing
- Diseñar pruebas
- Validar la funcionalidad respecto a requisitos
- Validad la usabilidad
- Encontrar errores 

- Ayudar al desarrollador identificando no sólo el error, sino donde está y porqué se produce

- Fomentar la calidad del código
- Dar tranquilidad a los desarrolladores


Fallo, error, defecto

Error algo que comete un humano -> Defecto dentro del producto -> Puede dar un fallo o no !
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Identificar causas raices !

# SonarQube ... Reglas para análisis

## Rules                Son reglas unitarias (miran una característica concreta) que aplican a un único lenguaje
                        En Java las variables deben comenzar con minúscula
                            miVariable
                        En python se usa snakecase
                            mi_variable
                        Por defecto cada regla lleva asociado:
                        - Criticidad de la incidencia (issue) si se incumple
                        - Tiempo estimado en la resolución de la incidencia
                        
                        Sonar trae una gran colección de reglas.. que se mantiene viva por parte de la gente de sonar
                        
                        Es posible añadir nuevas reglas:
                        - A través de plugins que instalamos en Sonar, desde su Administración > Marketplace 
                        - Pagando una licencia más cara -> Nuevas reglas para nuevos lenguajes de programación
                        - Programaticamente (desarrollo en JAVA) 
                        
                        JAVA 600
                        PYTHON 200
                        JS 400
                        
## Quality profiles     Es un conjunto de subconjuntos de las reglas definidas para cada lenguaje
                        Aquí defino las reglas que yo quiero que se apliquen a un proyecto / conjunto de proyectos
                        
                        Quality profiles: Reglas de proyectos CRITICOS DE LA EMPRESA
                            JAVA        500
                            PYTHON      180
                            JS          360
                            HTML         45
                        
                        Quality profiles: Reglas de proyectos MENOS CRITICOS DE LA EMPRESA
                            JAVA        300
                            PYTHON      150
                            JS          200
                            HTML         33
                        
                        Esta es la manera más sencilla que tenemos de activar / desactiavr reglas 
                        Al asignar/activar una regla para un determinado perfil (PROFILE) podemos cambiarle su criticidad
    
    Al hacer un análisis de código, se aplcian estas reglas... y de ellas se generan las incidencias (ISSUES):
    Los incumplimientos de reglas: bugs, smellcodes + vulnerabilidades
    
    Sonarqube nos muestra un listado de todos esos incumplimientos: ISSUES
    
    Sonar calcula una sumarización (resumen) desde esos incumplimientos -> METRICAS
            Numero de bugs
            Numero de bugs críticos
            Numero de bugs bloqueantes
            Numero de smell codes
            Deuda técnica
        Además calcula otro tipo de méticas
            Duplicación de código
            Cobertura de código
            % comentarios total

## Quality Gates
    
    Un quality gate: PUERTA DE CALIDAD es el mínimo que un proyecto debe puntuar en un conjunto de métricas, 
    para que sonar le dé el visto buenop
    
    Sonarqube trae un quality gate por defecto
    Esas puntuaciones mínimas, tenemos dos opciones:
        - Aplicarlas sobre todo el proyecto
        - Aplicarlas sobre el código nuevo que incluimos en el proyecto *** LEGACY


---
Vulnerabilidades:
                                                                  Jodete && sudo rm -rf /
Programa que pregunta al usuario:                                 Bienvenido
    Dame el mensaje que hay que mostrar al usuario de bienvenida |------------------|
Ese programa usa ese mensaje en otro sitio, para dar la bienvenida.. y es un programa que hago en la terminal de linux (bash)
    echo + MENSAJE DE BIENVENIDA
    
    echo Jodete && sudo rm -rf /

Si usamos una libreria a la que se le han detectado vulnerabilidades !
 Log4j !
 
---
Sistems de control de versión: CVS control version system

SCM: Source code manager

CVS -> SVN (Subversión) ->  git 
                                Servidores de alojamiento de repositorios remotos de git:
                                    Github      + Servidor de CI/CD
                                    Gitlab      + Servidor de CI/CD
                                    Bitbucket   + Bamboo
                            mercurial 