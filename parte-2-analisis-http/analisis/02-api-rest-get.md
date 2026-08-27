# Análisis 2: Petición GET — API REST Pública

## Información general
- URL: https://jsonplaceholder.typicode.com/posts/1
- Método: GET
- Código de estado: 200 OK (para recurso inexistente /posts/999: 404 Not Found)

## Headers de Request
| Header | Valor |
|--------|-------|
| Host | jsonplaceholder.typicode.com |
| User-Agent | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36 |
| Accept | text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8 |

## Headers de Response
| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | application/json; charset=utf-8 | Indica que la respuesta es una estructura de datos en formato JSON procesable por código. |
| Cache-Control | max-age=43200 | Define que el recurso puede ser almacenado en caché por el cliente durante 12 horas (43,200 segundos). |
| Access-Control-Allow-Credentials | true | Permite la inclusión de credenciales en peticiones CORS de origen cruzado. |

## Tiempos de carga
| Fase | Tiempo (ms) |
|------|------------|
| DNS Lookup | 2.15 ms |
| TTFB | 45.30 ms |

## Comparación HTTP vs API REST

| Aspecto | Petición HTML (Paso 7) | Petición API REST (Paso 8) |
|---------|-----------------------|----------------------------|
| Content-Type | `text/html; charset=UTF-8` | `application/json; charset=utf-8` |
| Propósito | Renderizar interfaz gráfica en navegador | Intercambio de datos estructurados entre cliente y servidor |
| Estructura de respuesta | Documento markup (`<html>`, `<body>`) | Objeto clave-valor JSON (`{ "userId": 1, "id": 1, ... }`) |
| Manejo de recurso inexistente | Redirección o página de error visual 404 HTML | Respuesta JSON vacía `{}` o error estructurado con código 404 |

## Conclusión
La petición GET al endpoint `/posts/1` retornó un estado `200 OK` junto con un payload estructurado en formato JSON, a diferencia de la petición a `example.com` que devolvió marcado HTML. Al consultar un recurso inexistente como `/posts/999`, el servidor respondió correctamente con un código de estado `404 Not Found`, confirmando la implementación semántica adecuada de las respuestas HTTP en arquitecturas RESTful. El encabezado `Content-Type: application/json` es el diferenciador clave que instruye al navegador o cliente a interpretar la respuesta como información estructurada de datos y no como un documento renderizable.