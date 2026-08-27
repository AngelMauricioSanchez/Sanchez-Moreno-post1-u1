# Análisis 1: Petición GET — example.com

## Información general
- URL: https://example.com/
- Método: GET
- Código de estado: 304 Not Modified

## Headers de Request
| Header | Valor |
|--------|-------|
| Host | example.com |
| User-Agent | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36 |
| Accept | text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7 |

## Headers de Response
| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | text/html; charset=UTF-8 | Define el tipo de recurso retornado (documento HTML) y la codificación de caracteres. |
| Cache-Control | max-age=604800 | Indica la directiva de almacenamiento en caché; el recurso se considera fresco por 604,800 segundos (7 días). |

## Tiempos de carga
| Fase | Tiempo (ms) |
|------|------------|
| DNS Lookup | 0.003 ms (3 µs) |
| TTFB | 61.86 ms |

## Conclusión
La petición HTTP efectuada a `example.com` devolvió un código de estado `304 Not Modified`, lo que indica que el navegador tenía el documento almacenado previamente en caché y el servidor validó que la versión local sigue siendo exactamente la misma (comprobado mediante el encabezado `If-Modified-Since` y `Etag`). Debido a esta validación, el servidor no retransmitió el cuerpo completo del documento HTML en la red, optimizando el ancho de banda. La fase de resolución DNS tomó únicamente 3 microsegundos gracias a la caché DNS local, mientras que el Time to First Byte (TTFB) de 61.86 ms refleja la latencia rápida de la red y la verificación realizada por la CDN de Cloudflare.
