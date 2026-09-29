# taller-postman-Luis_Armando_Perez_Isaza
## Marco Conceptual 
### ¿Que es una API REST?
Una API REST es una interfaz que permite que diferentes aplicaciones se comuniquen entre sí mediante peticiones HTTP. Utiliza métodos como GET, POST, PUT y DELETE para consultar, crear, actualizar o eliminar información de un servidor. Las API REST trabajan con recursos, por ejemplo productos o clientes, y comúnmente utilizan JSON para enviar y recibir los datos. En pocas palabras, permite que una aplicación pueda solicitar y manejar información de otra aplicación de una manera organizada y estandarizada.
[IBM - ¿Qué es una API REST?](https://www.ibm.com/mx-es/think/topics/rest-apis)
### ¿Que es un endpoint  de API?
Un endpoint es la ubicación específica, normalmente una URL, donde una API recibe las solicitudes para acceder a un recurso o realizar una función. Es el punto de contacto entre una aplicación cliente y el servidor. Por ejemplo, en una API REST, GET /api/productos sería un endpoint utilizado para solicitar los productos.
[IBM-¿Que es un endpoint?](https://www.ibm.com/mx-es/think/topics/api-endpoint)
### Ejemplo 
Un ejemplo muy común es WhatsApp. Cuando envías un mensaje, la aplicación se comunica con los servidores mediante diferentes APIs para enviar y recibir mensajes, compartir archivos, consultar información de contactos, realizar llamadas, etc. Por ejemplo, cuando envías una imagen, la aplicación realiza solicitudes al servidor mediante una API para subir la imagen y posteriormente permitir que el destinatario la descargue.
## Los Metodos HTTP
### Los métodos HTTP y el CRUD
| Método | Operación CRUD | Qué hace |
|---|---|---|
| GET | Leer | Obtiene información de uno o varios registros |
| POST | Crear | Crea un nuevo registro |
| PUT | Actualizar | Actualiza completamente un registro |
| PATCH | Actualizar | Actualiza parcialmente un registro |
| DELETE | Eliminar | Elimina un registro |
## Codigos de estados
### Las familias de códigos de estado
| Familia | Significado | Ejemplo |
|---|---|---|
| **1xx** | Respuestas informativas. Indican que la solicitud fue recibida y que el proceso continúa. | **100 Continue**: el servidor indica que el cliente puede continuar enviando la solicitud. |
| **2xx** | Respuestas satisfactorias. Indican que la solicitud se procesó correctamente. | **200 OK**: la solicitud fue realizada correctamente. |
| **3xx** | Redirecciones. Indican que el cliente debe realizar otra acción para completar la solicitud. | **301 Moved Permanently**: el recurso fue trasladado permanentemente a otra URL. |
| **4xx** | Errores del cliente. La solicitud tiene algún problema relacionado con lo que envió o solicitó el cliente. | **404 Not Found**: el servidor no encuentra el recurso solicitado. |
| **5xx** | Errores del servidor. El servidor tuvo un problema al intentar procesar una solicitud que recibió. | **500 Internal Server Error**: ocurrió un error interno inesperado en el servidor. |
### ¿Por qué se separan los errores 4xx de los 5xx?
La diferencia principal está en dónde se encuentra el problema. Los códigos 4xx indican que el problema está relacionado con la solicitud del cliente. Por ejemplo, si un usuario solicita una URL que no existe, el servidor puede responder con 404 Not Found. En cambio, los códigos 5xx indican que el servidor encontró un problema al intentar procesar una solicitud que recibió correctamente. Por ejemplo, un 500 Internal Server Error significa que el servidor encontró una situación inesperada que le impidió completar la solicitud.
En otras palabras, 4xx normalmente significa "revisa lo que estás solicitando o enviando", mientras que 5xx significa "el servidor tuvo un problema al procesarlo". No significa necesariamente que una persona tenga literalmente la "culpa": es una forma de clasificar el origen del problema desde el punto de vista de HTTP.
## Lee un recurso y la colección completa
### El código de estado
las dos peticiones fueron 200
### Cuántos elementos trae la respuesta
la primera solo trae un elemento y la segunda traes todos lo recursos 
### Qué campos tiene cada elemento
tiene los campos UserId, id, tittle y body 
### ¿en qué se diferencian los criterios de aceptación cuando pides un recurso y cuando pides una colección?
cuando pides un recurso tiene que poner un id para poder identificarlo y para una colecion solo tiene que ejecutar el endpoint
## Provoca un error a propósito
### ¿Este caso de prueba pasó o falló?
el caso de prueba paso ya que esperabamos un 404 ya que el elemento no existe en la base de datos(pagina de prueba) y ejecutamos el endpoint y efectivamente fue un 404
### ¿qué pasaría si esa misma petición hubiera devuelto 200 con un cuerpo vacío? ¿Sería un defecto?
si seria un defecto porque el codigo 200 significa se proceso correntamente pero al no devolver nada siendo un peticion tipo get seria un defecto ya que estaria vacion cuando esperabamos un elemneto 
## Crea un recurso con POST
### ¿qué observaste? ¿Por qué crees que ocurre eso? ¿Cómo comprobarías, en una API real, que el recurso se creó de verdad?
al ejecutarla 5 veces seguidas me devolvia el id 101 en cada una de las 5 ocasiones esto ocurre porque es una api gratuita orientada para temas academicos y para aprender sobre las apis en un api real me hubiera delvovido los ids 101,102,103,104 y 105 asi sumando el ultimo id del ultimo elemento cada vez que se ejecuta la peticion post


