#
## Tabla de Peticiones 
| # | Petición | Código esperado | Código obtenido | ¿Coincide? |
|---|---|---|---|---|
| 1 | GET /posts/1 | 200 | 200 | si |
| 2 | GET /posts | 200 | 200 | si |
| 3 | GET /posts/9999 | 404| 404 | si |
| 4 | POST /posts | 200 | 201 | no |
| 5 | PUT /posts/1 | 404 | 200 | no |
| 6 | PATCH /posts/1 | 200 | 200 | si |
| 7 | DELETE /posts/1 | escríbelo antes | — | — |
## La diferencia entre PUT y PATCH
### ¿qué diferencia encontraste entre ambas respuestas? ¿Cuál usarías para corregir un error de escritura en un solo campo, y por qué?
el put reemplaza todo el objeto si mandas solo un campo por ejemplo tittle todo lo demas se borrara y quedara solo tittle y en patch es para actualizar parcialmente si manda tittle se actualizara y dejara los otros campos intactos, para corregir un error de escritura en un solo campo usaria patch ya que modificar los campos que se manda por ejemplo tittle y body si se manda esos dos son los unicos que se van a modificar los otros campos queda intactos
## peticion put 
{
    "tittle": "prueba",
    "id": 1
}
## peticion patch
{
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto",
    "tittle": "prueba"
}
## Encontrando el limite
Para encontrar el límite de publicaciones de la API, probé los IDs **100 y 101**. Al realizar la petición `GET /posts/100`, la API respondió con **200 OK**, lo que indica que la publicación existe. Luego, al realizar la petición `GET /posts/101`, la API respondió con **404 Not Found**, indicando que esa publicación no existe.

Por lo tanto, el **ID 100 es el último ID válido** y el **ID 101 es el primer ID que devuelve un error 404**.

Este tipo de prueba se conoce como **prueba de valores límite** (*Boundary Value Analysis*). Se utiliza para comprobar el comportamiento de un sistema justo en los límites de un rango, ya que es común que los defectos aparezcan en estos puntos debido a errores en las condiciones o restricciones del programa.
