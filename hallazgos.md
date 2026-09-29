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
