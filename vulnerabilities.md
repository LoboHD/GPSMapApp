# Reporte de vulnerabilidades

## Sumario
  Total de vulnerabilidades encontradas: 5
  Criticas: 2
  Altas: 2
  Media: 0
  Baja: 1
  
## Detalles encontrados
### 1. Vulnerabilidad firma de certificado de depuracion
  * Descripcion: La aplicaicon esta firmada con un certificado de depuracion, el cual no
    es apropiado para un entorno de produccion.
  * Severidad: Alta.
  * Impacto: Si la aplicacion llega a ser atacada, se podria hacer una ingenieria inversa,
    modificar codigo o poner un malware debido a que los certficados de depuracion no
    ofrece una proteccion.
  * Paso a Paso:
    1.- Se indentifico que la firma del APK fue realizada con un certificado de depuracion.
    2.- Un atacante puede usar esto para inspeccionar y modificar el codigo de la
        aplicacion
  * Mitigacion:
    1.- Utilizar un certificado de produccion y no de depuracion
    2.- Implementar una ofuscacion de codigo para que sea mas dificil de realizarle una
        ingenieria inversa de la aplicacion.

### 2. Vulnerabilidad depuracion habilitada en la aplicacion
  * Descripcion: La opcion de depuracion esta habilitada, lo cual permite a cualquier
    persona con conocimientos ingresar a la aplicacion y ver como funciona.
  * Severidad: Alta
  * Impacto: Facilita a un atacante que pueda conectarse con un depurador, el cual podria
    interceptar datos o modificar el comportamiento de la aplicacion.
  * Paso a Paso:
    1.- Se detectó que la propiedad android:debuggable=true está activada en el archivo
        AndroidManifest.xml.
    2.- Esto permite que cualquier persona con acceso al dispositivo pueda conectarse a
        la aplicación y extraer información valiosa.
  * Mitigacion:
    1.- Tenemos que asegurarnos de desactivar la opcion de depuracion cuando la
        aplicacion este lista al momento de que pueda lanzarse.

### 3. Vulnerabilidad Permisos de ubicacion.
  * Descripcion: Tu aplicacion solicita permisos acceder a la ubicacion del usuario.
  * Severidad: Media.
  * Impacto: Si una aplicacion maliciosa logra acceder a estos permisos, podria obtener
    la ubicacion de los usuarios sin que ellos lo sepan. Lo cual afectaria a la privacidad
    de los usuarios.
  * Paso a Paso:
    1.- La aplicacion solicita permisos para obtener la ubicacion precisa del usuario.
    2.- Esto podria ser explotado por una aplicacion maliciosa para rastrear a los usuario
        si los permisos no son gestionados correctamente.
  * Mitigacion:
    1.- Revisar que los permisos sean estrictamente necesarios para la aplicacion.
    2.- Implementar un manejo responsable de la informacion de la ubicacion.

### 4. Vulnerabilidad Receptor de broadcast exportado
  * Descripcion: El componente de la aplicacion Broadcast Receiver esta configurado para
    ser accesible por otras aplicaciones, lo que significa que otras aplicaciones podrian
    enviar informacion.
  * Severidad: Media.
  * Impacto: Al estar abierto este receptor a otras aplicaciones, podria ser utilizado para
    ser usado para fines malintencionados, como enviar datos manipulados o alterar el
    funcionamiento de la app.
  * Paso a Paso:
    1.- El receptor ProfileInstallReceiver esta exportado, eso significa que otra aplicaciones
    podria interactuar con esta.
    2.- Si una aplicacion maliciosa obtiene los permisos, podria enviar mensajes al receptor y
    alterar las funciones de la app.
  * Mitigacion:
    1.- Si el receptor no necesita interactuar con otras aplicaciones, debemos configurarlo
    para que este no pueda ser exportado.
    2.- Asegurarnos de que los permisos relacionados con este receptor que este bien protegido
    y tenga un nivel adecuado de seguridad, para que solo aplicaciones confiables puedan
    interactuar con el.
    
