
SCM
Hacen seguimiento del codigo fuente en ramas, son caminos paralelos que toma el código 

En cada rama vamos guardando fotos del proyecto: COMMIT

COMMIT 1 para el ALTA DEL PROYECTO: Incluye una foto/snapshop/copia de seguridad completa del estado del proyecto en ese momento
COMMIT 2 con unos cambios:          Incluye una foto/snapshop/copia de seguridad completa del estado del proyecto en ese momento



GIT es un sistema de control un poco especial

    GIT es un sistema de control de versión DISTRIBUIDO
    
    Cada usuatio tiene su propio repo en su maquina loca, distinto del resto de los usuarios
    
                    Repo REMOTO
                    Main Desarrollo         Repo REMOTO
                    1 2 3Ig 4I
                        |                       |
          -----------------------------------------------
          |                                             |
        IVAN PC                                     IGNACIO PC
          |                                             |
        REPO GIT                                    REPO GIT
        Ivan Main Desarrollo remoto/main           Main Desarrollo Ignacio
               1                     1               1
                    1                                2
         1                                           3Ig
         2          
                    2
               2.                    2
         3I
                    3I
               3I                   3Ig
               
               4I                   4I
               
               
Pull = fetch + merge
Pull = fetch + rebase


Trunk -> Master -> Main -> Aqui no se puede hacer ningún commit . El código que hay aqui se considera listo para producción
                    \
                     \ Desarrollo
                                 \ Desarrollador Ivan
                                 \ funcionalidad 17


Servidor de automatización JENKINS    AZUREDEVOPS 
                            v
                            REPO REMOTO GIT
                            
HOST
    CONTENEDOR PostgreSQL
    CONTENEDOR SONAR
    CONTENEDOR Jenkins *
    CONTENEDOR ENTORNO DE PRUEBAS 1 -> test, empaquetado, lanzar analisis de sonarqube... 