# Instrucciones para ejecutar y probar el lector de códigos de barras de productos
## Instalación de dependencias
1. Descargue "Eclipse IDE for Enterprise Java and Web Developers" desde este [enlace](https://www.eclipse.org/downloads/packages/), seleccionando la versión correspondiente a su sistema operativo.
2. Descomprima el archivo descargado.

## Configuración del proyecto
1. Acceda a [Spring Initializr](https://start.spring.io/), no modifique ninguno de los campos de **Project Metadata** y seleccione las siguientes opciones:
    - Project: Maven
    - Languaje: Java
    - Spring Boot: 3.4.1
    - Packaging: Jar
    - Java: 17
    - Dependencies: Haga clic en el botón 'ADD DEPENDENCIES' y seleccione Spring Web.

2. Haga clic en el botón 'GENERATE'.
3. Descomprima el archivo descargado para obtener la carpeta del proyecto.
4. Inicie "Eclipse IDE for Enterprise Java and Web Developers".
5. Importe el proyecto en Eclipse siguiendo los siguientes pasos:
    - 5.1. Haga clic en **File > Import**.
    - 5.2. Escriba *Existing Maven Projects* en el campo **Select an import wizard**, seleccione **Existing Maven Projects** y haga clic en **Next**.
    - 5.3. En el campo **Root Directory** seleccione la carpeta descomprimida del proyecto y haga clic en **Finish**. Eclipse descargará las dependencias necesarias y configurará el proyecto automáticamente. Este proceso puede tardar unos minutos dependiendo de la velocidad de tu conexión a internet.

6. Clone este repositorio.
7. Importe el lector de códigos de barras de productos en Eclipse siguiendo los siguientes pasos:
    - 7.1. Navegue al paquete **com.example.demo** del proyecto importado. Para hacerlo, haga clic sobre el proyecto y luego sobre la carpeta **src/main/java** en el panel lateral izquierdo.
    - 7.2. Haga clic derecho sobre el paquete **com.example.demo** y seleccione **Import**.
    - 7.3. Escriba *File System* en el campo **Select an import wizard**, seleccione **File System** y haga clic en **Next**.
    - 7.4. En el campo **From directory** seleccione la carpeta **src** del repositorio clonado.
    - 7.5. Marque la carpeta **src** en el campo izquierdo y haga clic en **Finish**.

## Ejecución y prueba
Antes de probar el funcionamiento del lector de códigos de barras de productos, es importante tener en cuenta lo siguiente:
- Si el código de barras es válido, el programa devolverá una respuesta JSON que incluye el código de barras, el lote extendido y el bulto.
- Si el código de barras no es válido, el programa devolverá una respuesta JSON con un mensaje de error indicando el problema.

1. En Eclipse haga clic derecho sobre la carpeta **src/main/java** y diríjase a **Run As**.
2. Seleccione **Java Application** para ejecutar el lector de códigos de barras de productos.

A continuación, se describen dos alternativas para realizar las pruebas.

### Prueba con un navegador web
1. Copie el siguiente URL ```http://localhost:8080/api/barcodereader/<barcode>``` y péguelo en la barra de búsqueda de un navegador web.
2. Reemplace `<barcode>` por un código de barras y presione Enter.

### Prueba con POSTMAN
1. Inicie POSTMAN.
2. Importe el archivo ```Peticiones de la API REST del lector de códigos de barras de productos.postman_collection.json``` que se encuentra en la carpeta **colección POSTMAN** del repositorio clonado.
3. Abra una de las peticiones del archivo importado y haga clic en el botón **Send**. POSTMAN mostrará la respuesta de la API REST, que puede ser un JSON con los datos esperados o un mensaje de error, dependiendo del código de barras ingresado.