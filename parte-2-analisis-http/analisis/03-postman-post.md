# Análisis 3: Petición POST Simulada con Postman

## Evidencia de la Petición y Tests
![Postman POST Request](../capturas/03-postman-post.png)

## Configuración de la petición
- **URL:** `https://jsonplaceholder.typicode.com/posts`
- **Método:** `POST`
- **Headers enviados:** `Content-Type: application/json`

### Cuerpo enviado (Payload)
```json
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1
}

Respuesta recibida
Código de estado: 201 Created

Tiempo de respuesta: 30 ms

Headers de Response relevantes
Content-Type: application/json; charset=utf-8 — Indica que la respuesta procesada es un JSON válido.

Cache-Control: no-cache — Indica que la respuesta no debe ser almacenada en caché.

Access-Control-Allow-Credentials: true — Permite el intercambio de recursos de origen cruzado (CORS).

Etag: W/"7f-+oN5bcd5gPS3m4JG6wRHEiiFBkA" — Identificador único para validar la versión del recurso retornado.

Cuerpo devuelto por el servidor
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1,
  "id": 101
}

Pruebas automatizadas (Postman Tests)
Se agregaron las siguientes aserciones en la pestaña Scripts / Post-response:
pm.test("Status 201 Created", () => {
  pm.response.to.have.status(201);
});

pm.test("Respuesta incluye id asignado", () => {
  const json = pm.response.json();
  pm.expect(json).to.have.property("id");
  pm.expect(json.title).to.equal("Laboratorio Programacion Web");
});

Resultados obtenidos
PASS - Status 201 Created

PASS - Respuesta incluye id asignado

Diferencias entre peticiones GET y POST
Propósito principal: GET consulta u obtiene datos existentes; POST envía datos para crear o procesar un recurso.

Cuerpo del mensaje (Body): GET no utiliza cuerpo; POST incluye payload (JSON, Form-data, etc.).

Idempotencia: GET es idempotente (ejecutarlo N veces no altera los datos); POST no es idempotente (cada llamada crea un recurso nuevo).

Código de respuesta estándar: GET responde 200 OK (o 304 Not Modified); POST responde 201 Created.

Conclusión
La petición POST ejecutada a través de Postman envió con éxito el cuerpo de datos en formato JSON, simulando la inserción de un nuevo registro en la API pública. El servidor respondió con el código de estado 201 Created y retornó el objeto con su correspondiente propiedad id generada (101). Las pruebas automatizadas escritas en JavaScript confirmaron satisfactoriamente la validez semántica de la respuesta y el cumplimiento de las condiciones requeridas.