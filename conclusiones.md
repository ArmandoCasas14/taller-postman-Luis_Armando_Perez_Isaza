#Conclusiones 
## Idempotencia 
Un método HTTP es idempotente cuando realizar la misma petición varias veces produce el mismo efecto en el servidor que realizarla una sola vez. Esto es útil, por ejemplo, cuando una petición falla y es necesario volver a enviarla.
| Método | ¿Idempotente? | Ejemplo |
|---|---|---|
| **GET** | Sí | Consultar un producto varias veces no lo modifica. |
| **POST** |  No | Crear un producto varias veces puede crear varios productos. |
| **PUT** |  Sí | Actualizar un producto con los mismos datos varias veces deja el mismo resultado. |
| **PATCH** |  No* | Una modificación parcial puede producir efectos diferentes si se repite. |
| **DELETE** |  Sí | Eliminar un producto varias veces mantiene el recurso eliminado. |
Compruébalo en Postman: ejecuta varias veces la misma petición PUT y luego varias
veces la misma POST. ¿Qué diferencia observas en el resultado?
dan el mismo resulta al ser una api pedagogica que busca que enseñar el funcionamiento pero en un real el post agregaria el mismo producto con diferente id