# Sonarqube

- Que elija usarla. REFACTORIZACION
- Que me la impongan

# Qué información me devuelve

## Información detallada

## Métricas generales

### Complejidad

- Complejidad ciclomática
  
  Número de caminos que puede tomar un código al ser ejecutado: BUSCAMOS MAXIMIXARLA O MINIMIZARLA?
  Ninguna de las dos. Los caminos distintos los marca: LA LOGICA QUE QUIERO IMPLEMENTAR.
      
        if edad > 18:
            if edad < 33:
                pasa pagando
            else:
                pasa gratis 
        else:
            no pasa 
            
            Complejidad ciclomatica? 3 caminos < Logica del negocio / requerimientos funcionales

  Este dato es importante de cara a determinar el número mínimo de PRUEBAS que debo realizar !

- Complejidad cognitiva
  
  Cómo de complejo es para un ser humano entender ese código:  BUSCAMOS MAXIMIXARLA O MINIMIZARLA?
    MINIMIZARLA !

    # Ejemplo 1                                  # Ejemplo 2
    
    //Hago algo A                                // Hago algo A
    if condicion1:                               switch VARIABLE:
        if condicion2:                              case 1: //Hago algo B
            //Hago algo B                           case 2: //Hago algo C
        else if condicion3:                         case 3: //Hago algo D
            //Hago algo C                           case 4: //Hago algo E
        else:                                       case 5: //Hago algo F
            //Hago algo D                           case default: //Hago algo G
    else if condicion4:
        if condicion5:
            //Hago algo E
        else:
            //Hago algo F
    
    Complejidad ciclomatica: 6                  Complejidad ciclomática: 6
    
    Opciones:   A                                   A, B
                A, B                                A, C
                A, C                                A, D
                A, D                                A, E
                A, E                                A, F
                A, F                                A, G

    > La complejidad cognitiva del ejemplo 2 es muy inferior a la del ejemplo 1


# Orden de complejidad de un algoritmo. 

Algoritmia. Orden de Complejidad de un algoritmo. O(n) O(n·log(n)) 

Cómo crece el número de operaciones que debe hacer la computadora para ejecutar 
ese algoritmo según entran más y más datos.
Esto es importante si monto una BBDD

### Duplicaciones

- Trozos de código repetidos                  \
- Numero de lineas de código repetidas         >  REFACTORIZAR... create una función única
- Porcentaje de lineas de codigo repetidas    /
- Ficheros repetidos                          Me tocará quedarme con 1

### MANTENIBILIDAD

- Code smells: APESTOSIDADES EN EL CODIGO: Se tasan cuantitativamente : CANTIDAD : 1736 -> NOTA A->F
    
    Malas prácticas: 
        Meter un return en medio de una función 

        Variables mal nombradas
                    
                    variable: numero de hijos       clase: familia politica     constante: padre
            JAVA    numeroDeHijos                    FamiliaPolitica                PADRE
            PYTHON  numero_de_hijos                                                 _padre
        
        JAVA:
            System.out.println() <-> Logger
    
        Dejar un código comentado

  ME INTERESA MINIMIZARLA

Esos smell codes, SonarQube los tasa también en horas de trabajo... El tiempo que me llevaría arreglar esas chapucillas

- Deuda Técnica: Tiempo: Horas, dias, minutos

  En algún momento voy a tener que pagarla. Cuándo? Ahora, o cuando haya un bug?
  
  ME INTERESA MINIMIZARLA
 
### TAMAÑO DEL CODIGO

- Clases
- Número de funciones
- Lineas de código
- Comentarios <<< CHEQUEO: % de comentarios mínimo 15% 10%

### TEST - Pruebas unitarias

- Cobertura de código: El porcentaje de lineas de código cubiertas por casos de pruebas (test unitarios) < 80%

Las pruebas unitarias pueden acabar en 3 estados diferentes:
- OK . Se obtuvo el resultado esperado
- KO . No se obtuvo el resultado esperado
- ERROR, OSTION, EXPLOSION GIGANTE . No hay resultado. Reventó !

Pregunta... Es habitual encontrar test fallidos en Sonarqube? Es bueno?
- TDD:
- Dia 1: Defino todas las pruebas -> Explotan todas ...No hay codigo que haga nada

NUMERO DE FALLOS
            XX      XX      XX      XX      
            XXXX    XXXX    XXXX    XXXX    
            XXXXXX  XXXXXX  XXXXXX  XXXXXX  
            XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
                                                TIEMPO
                                                
            X   X   X   X   X   X   X   X   X   X   
           XXX XXX XXX XX   X  XX  XX   XX  XX  X

Sonarqube obtiene un informe de pruebas unitarias ejecutadas por un tercero y lo analiza.


# 3 bloques grandes en sonarqube:

- Instalación: CHUPETE !
- Mantenimiento de las reglas <<<<  PERFIL 1
- Integración de sonarqube con otras herramientas <<<<<< PERFIL 2   Depende de la herramienta con quien quiera integrarlo
- Usuario >> Lo único que necesito es saber interpretar la info que da de vuelta
