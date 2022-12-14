# Modelo de instalación tardicional

         App1 + App2 + App3           Problemas:
    ----------------------------        Incompatibilidades entre las apps o sus dependencias, librerias, configuraciones
          Sistema operativo             Seguridad
    ----------------------------        App1 (BUG - 100% CPU) -> OFFLINE
           Hierro                               APP2 y APP3 ---> OFFLINE
           
# Modelo de basado en máquinas virtuales

         App1 |    App2 + App3          Problemas:
    ----------------------------            Incrementa la complejidad de la instalación / mnto
        SO 1  |        SO 2                 Merma de recursos
    ----------------------------            Empeoramiento en el rendimiento de las apps
        MV 1  |        MV 2
    ---------------------------- 
          Hipervisor:
          Vmware, citrix, hyperv
          virtualbox, kvm
    ---------------------------- 
          Sistema operativo      
    ---------------------------- 
              Hierro                
           
# Modelo de basado en contenedores

         App1 |    App2 + App3          
    ----------------------------  
        C 1   |        C  2
    ---------------------------- 
      Gestor de contenedores:
      Docker, Podman, CRIO, 
      Containerd
    ---------------------------- 
      Sistema operativo Linux     
    ---------------------------- 
              Hierro                


# Contenedores

> Es un entorno aislado dentro de un SO con kernel Linux donde ejecutar procesoS.

> Aislado:
- Tiene su propia configuración de red, independiente del host: Su propia IP
- Tiene su propio sistema de archivos
- Tiene sus propias variables de entorno
- Puede tener limitación de acceso a los recursos hardware de la máquina

Los contenedores se crean desde IMAGENES DE CONTENEDOR

# Imagen de contenedor

Es un triste archivo comprimido (tar) que contiene:
- UNA APLICACION YA INSTALADA POR ALGUIEN (que sabe un huevo más que yo de instalar esa aplciación)
    Habitualmente el fabricante de ese software 
- CON UNA PRECONFIGURACION 100% funcional, que yo podré parametrizar hasta cierto punto
- CON LAS LIBRERIAS Y DEPENDENCIAS NECESARIAS PARA QUE AQUELLO FUNCIONE
- + OTRO SOFTWARE OPCIONAL QUE PUEDA SER DE AYUDA PARA MI

Además se incluyen algunas configuraciones que se usaran por defecto cuando se cree un contenedor desde esa imagen.

Las imagenes de contenedor las encontramos en REGISTRIES DE REPOSITORIOS DE IMAGENES DE CONTENEDOR:
- Docker hub
- Quay.io       < Redhat


x Una foto de una configuración
x Un SO que corre un único proceso
x Una virtualización con un sistema operativo
x Una micromáquina virtual con lo mínimo necesario para ejecutar algo

# Imagen de contenedor

√ Una aplicación empaquetada con todo lo que necesita para funcionar


Quiero instalar Mongo DB en mi maquina.
Qué hago?
PASO 1: tengo la maquina fetén para instalar el mongo... requerimientos y demás
PASO 2: Descargar instalador de MongoDB?
PASO 3: Ejecuto instalador ... que ya tengo que saber un huvo de mongo... y configuro el mongo
PASO 4: Arranco el mongo.
----> c:\archivos de programa\mongodb ---> .zip ---> email
                                            vv
                                            Imagen de contenedor
                                            
                                            
docker cp contenedor:/datos /home/ubuntu/misdatos

sudo su -
sysctl -w vm.max_map_count=262144
echo vm.max_map_count=262144 > /etc/sysctl.conf
exit