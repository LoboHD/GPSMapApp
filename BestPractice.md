## Reporte de buenas practicas

### Ceritifcado de depuracion
  * Descripcion: La aplicaion al estar firmada con un certificado de depuacion, el cual cual es un
    riesgo para el cliente cuando se lanza al publico ya que algun ataque malicioso podria lograr
    una filtracion de la informacion de los clientes/usuarios.
  * Buenas practicas:
    1.- Usar certificados de poduccion y no de depuracion al momento de lanzar
    la aplicacion al publico
    2.- Mantener la clave en un lugar seguro.

### Depuracion Habilitada
  * Descripcion: La aplicacion tiene las opciones de depuracion activadas, eso permite a personas
    malintencionada espiar o tener una puerta trasera para ver el funcionamiento de la app y extrar
    informacion.
  * Buenas practicas:
    1.- Verifica en el "AndroidManifest.xml" que las propiedades "debuggable" esten  eliminandas o
    deshabilidas.
    2.- Mantener el desarrollo con la produccion en distintos ambientes.

### Permisos de Ubicacion peligrosos
  * Descripcion: La aplicacion solicita permisos que permiten rastrear la ubicacion del usuario,
    lo cual puede ser utilizado por aplicaciones maliciosas.
    Buenas practicas:
    1.- Implementar una solicitud dinamica de los permisos, para solo obtener los permisos cuando
    el cliente este utilizando la app.
    2.- Proporcionar politicas de privacidad que explique para que se utilizazra la ubicacion.
    3.- Limitar el uso de servicios cuando no sea necesario.

### Receptor de broadcast accesibles:
  * Descripcion: Uno de los componentes de la app esta abierto lo cual significa que otras aplicaciones
  * puedan interactuar con ella.
    Buenas practicas:
    1.- Marcar el broadcast como falso para que no pueda ser utilizado por otras aplicaciones.
    2.- Solo permitir que aplicaciones confiables puedan interactuar con la nuestra.

### Proteccion de permisos 
  * Descripcion: Los permisos de receptor de broadcast no estan completamente protegidos, el cual
    puede ser utilizado por atacantes.
    Buenas practicas:
    1.- Verifcar los permisos asignados en el manifiesta y asegurarnos que los permisos criticos
    esten en un nivel de acceso adecuado.


    
