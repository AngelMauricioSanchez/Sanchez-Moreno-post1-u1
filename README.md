# Sanchez-Moreno-post1-u1
Laboratorio — Configuración del entorno y análisis de peticiones HTTP

# Post-contenido — Unidad 1: Fundamentos de la Web

## Descripción
Repositorio del laboratorio de la Unidad 1 de Programación Web —
Séptimo Semestre. Contiene dos partes: configuración del entorno
de desarrollo (parte-1-entorno/) y análisis de peticiones HTTP con
Chrome DevTools y Postman (parte-2-analisis-http/).

## Parte 1 — Entorno de desarrollo
Página HTML básica inspeccionada con Chrome DevTools. Ver
parte-1-entorno/.

## Parte 2 — Análisis de peticiones HTTP
| # | Tipo | URL | Código |
|---|------|-----|--------|
| 1 | GET HTML | https://example.com | 304 Not Modified |
| 2 | GET JSON (exitoso) | https://jsonplaceholder.typicode.com/posts/1 | 200 OK |
| 3 | GET JSON (fallido) | https://jsonplaceholder.typicode.com/posts/999 | 404 Not Found |
| 4 | POST JSON | https://jsonplaceholder.typicode.com/posts | 201 Created |

Ver parte-2-analisis-http/analisis/.

## Herramientas utilizadas
- VS Code, Git, GitHub
- Google Chrome + DevTools (panel Network)
- Postman (petición POST con tests)

## Conclusiones
En esta práctica se afianzaron los conocimientos fundamentales del entorno de desarrollo web y el control de versiones con Git y GitHub. A través de la inspección con Chrome DevTools y el uso de Postman, se comprendió el comportamiento de las peticiones HTTP, diferenciando el intercambio de documentos HTML de la transferencia de datos estructurados en formato JSON. Se analizó la semántica de los códigos de estado HTTP (200, 304, 404 y 201) y la diferencia clave entre peticiones GET y POST en arquitecturas RESTful. Finalmente, la implementación de pruebas automatizadas en Postman permitió validar con precisión las respuestas del servidor y la integridad de los datos.