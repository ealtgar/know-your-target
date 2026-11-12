# 1
### Comparativa General

|**Característica**|**cuaderno.md (Humano)**|**IA (informe.md, trazas)**|
|---|---|---|
|**Metodología**|Ejecución manual mediante CLI (bash, `curl`, `jq`) y scripts iterativos.|Ejecución automatizada y paralela mediante invocación de herramientas internas.|
|**Formato del entregable**|Cuaderno de bitácora/Writeup. Muestra el "cómo" (comandos de terminal) y el razonamiento.|Reporte ejecutivo formal. Muestra resultados directos organizados en tablas y omite la ejecución.|
|**Resolución DNS**|Uso manual de `dig` para registros individuales y bucles `while` para resolver IPs masivamente.|Uso concurrente de la herramienta `dns_registros` mapeando múltiples subdominios rápidamente.|
|**Huella Tecnológica**|Dependencia de interfaces gráficas (Netcraft) ante la falta de API gratuita.|Uso nativo de `tecnologias_whatweb` para extraer cabeceras HTTP, servidores, CDNs y frameworks de forma masiva.|
|**Búsqueda de Correos**|Uso de plataformas OSINT externas de terceros (RocketReach, Hunter.io).|Uso de `correos_theharvester` consultando múltiples fuentes, aunque sin éxito en el hallazgo (0 resultados).|

|**Categoría de Hallazgo**|**Descubrimientos del Usuario (cuaderno.md)**|**Descubrimientos del Agente IA (informe.md y trazas)**|
|---|---|---|
|**WHOIS y Registros DNS**|Identificó los servidores de nombres de AWS y extrajo la IP `34.149.46.130` mediante consultas `dig`. Realizó WHOIS inverso sobre IPs descubriendo redes de Amazon, Salesforce y Zendesk.|Obtuvo fechas exactas de registro (2012-02-28 a 2034-02-28), identificó al registrador (GoDaddy) y extrajo masivamente registros A, MX, NS, SOA y múltiples registros TXT (SPF y verificaciones de dominio).|
|**Subdominios**|Recopiló un total de 298 subdominios únicos tras fusionar y limpiar manualmente los resultados de `subfinder` y `crt.sh`.|Identificó 221 subdominios mediante `crt.sh`, 264 mediante `subfinder` y 155 hosts a través de `theHarvester`.|
|**Correos Electrónicos**|Utilizó plataformas de terceros (RocketReach y Hunter.io) para evadir las limitaciones técnicas y buscar patrones de correo o empleados.|Ejecutó `theHarvester` consultando múltiples fuentes, pero obtuvo 0 correos electrónicos.|
|**Huella Tecnológica**|Identificó el uso de CDNs (Cloudfront), balanceadores de carga, Nginx y un LMS (Workramp) inspeccionando IPs específicas a través de Shodan.|Identificó los frameworks (Next.js, Express), servidores/proxies (API Gateway, Envoy, Google Frontend), y extrajo las cabeceras de seguridad HTTP (HSTS, CSP, X-Frame-Options) mediante `whatweb`.|
|**Ficheros Expuestos**|Encontró y analizó el contenido de `robots.txt` (incluyendo reglas para bots de IA y sitemaps) y `security.txt` (enlaces a HackerOne).|No buscó ni encontró ficheros expuestos en la raíz del servidor.|
|**Histórico Web (Wayback)**|Localizó archivos JSON sensibles (`ai-plugin.json`, `assetlinks.json`, `gpc.json`) buscando en el histórico de Wayback Machine.|No implementó búsquedas en el histórico del sitio.|
|**Google Dorks**|Ejecutó búsquedas avanzadas en Google (Dorks), aunque no obtuvo resultados relevantes.|No utilizó operadores de búsqueda avanzada en buscadores.

### Análisis de tu trabajo (`cuaderno.md`)

Mi enfoque destaca por una mentalidad investigativa mucho más amplia (OSINT) y la capacidad de sortear obstáculos que bloquean a los sistemas automatizados:

- **Profundidad OSINT:** Voy más allá del descubrimiento técnico estándar al incorporar técnicas como **Google Dorks**, revisión del **Histórico (Wayback Machine)** para buscar archivos JSON filtrados, y el análisis de **Ficheros Expuestos** (`robots.txt`, `security.txt`). La IA omitió por completo estos vectores.
- **Análisis de Servicios Expuestos:** Utilizo la API de _InternetDB_ de Shodan para inspeccionar puertos abiertos, vulnerabilidades y etiquetas (como "LMS" o "balanceadores de carga") basándome en las IPs descubiertas previamente.
- **Control manual de datos:** Realizo procesos de limpieza explícitos (ordenar y eliminar duplicados con `sort` y `uniq`) y decido de forma manual qué subdominios excluir (ej. `support.snapchat.com`).

### Análisis del Agente de IA (`informe.md` y trazas)

El enfoque del agente prioriza la velocidad, la estructuración ejecutiva y el reconocimiento técnico automatizado a nivel de infraestructura web:

- **Escaneo Concurrente:** Según los logs (`traza.jsonl.md`), el agente invoca herramientas simultáneamente y procesa docenas de peticiones HTTP en segundos.
- **Identificación de Infraestructura Web:** A través de WhatWeb, el agente extrae información muy precisa sobre cabeceras de seguridad (HSTS, CSP, X-Frame-Options), proxies (Envoy, Google Frontend), tecnologías de desarrollo (Next.js, Express) y CDNs específicos (Amazon CloudFront).
- **Manejo de Errores Silencioso:** Cuando herramientas como _Netcraft_ devuelven páginas bloqueadas por JavaScript, o cuando _crt.sh_ da un error "502 Bad Gateway" en el primer intento, el agente lo registra en la traza y continúa con otras fuentes (subfinder, theharvester) sin detener la ejecución global.
- **Síntesis Ejecutiva:** El documento final agrupa inteligentemente la infraestructura detectada (AWS Route 53, GCP, Google Workspace) proporcionando un resumen accionable, sin el ruido de los comandos intermedios.

---
---
# 2
## Informe Ejecutivo: Reconocimiento Pasivo Manual vs. Agente IA

Este parte del documento detalla las diferencias operativas, estratégicas y de formato entre el reconocimiento pasivo realizado manualmente (`cuaderno.md`) y el ejecutado por el agente de Inteligencia Artificial (`informe.md` y logs de traza).

### 1. Metodología y Ejecución

- **Enfoque Humano (Manual):** Secuencial e investigativo. Se basa en el uso de la interfaz de línea de comandos (CLI) combinando herramientas como `curl`, `jq`, `dig` y `subfinder` mediante scripts en _bash_ para automatizar tareas repetitivas (como la resolución de IPs con bucles `while`). Requiere intervención manual para la limpieza de datos (ej. ordenar y eliminar duplicados con `sort` y `uniq`) y la exclusión de subdominios fuera de alcance.
- **Enfoque IA (Automatizado):** Concurrente y declarativo. El agente orquesta múltiples herramientas nativas (`whois_dominio`, `dns_registros`, `tecnologias_whatweb`) de forma simultánea. Delega el procesamiento de la información a funciones internas, manejando excepciones (como el error 502 de _crt.sh_) de forma silenciosa sin interrumpir el flujo global del reconocimiento.

### 2. Alcance de la Superficie de Ataque

- **Profundidad OSINT (Humano):** Cubre vectores de reconocimiento no estructurados y de lógica empresarial. Incluye la revisión de archivos expuestos (`robots.txt`, `security.txt`), la búsqueda en el histórico de la web (Wayback Machine) para encontrar endpoints JSON, y la utilización intensiva de Google Dorks para descubrir paneles de login o documentos expuestos. Para la recolección de correos, recurre a bases de datos comerciales de terceros (RocketReach, Hunter.io).
- **Análisis de Infraestructura (IA):** Se centra estrictamente en la configuración técnica y de red. Extrae de forma masiva y estructurada las cabeceras HTTP de seguridad (HSTS, CSP), la identificación de proxies (Google Frontend, Envoy), los CDNs (Amazon CloudFront) y los frameworks de desarrollo (Next.js, Express). Su búsqueda de correos se limita a fuentes públicas agregadas (theHarvester), resultando en cero correos encontrados.

### 3. Formato y Entregable

- **Humano:** Un cuaderno de bitácora técnico (Writeup) que documenta el razonamiento, los comandos exactos introducidos y las salidas en bruto de la terminal (stdout).
- **IA:** Un reporte ejecutivo limpio. Omite el "cómo" y presenta directamente el "qué", estructurando los hallazgos en tablas consolidadas y listas de viñetas agrupadas por componentes (DNS, Hosting, CDN).

### Tabla Comparativa de Capacidades

|**Característica Evaluada**|**Ejecución Manual (cuaderno.md)**|**Agente IA (informe.md / trazas)**|
|---|---|---|
|**Resolución DNS**|Individual / Scripts `bash` personalizados|Mapeo rápido y masivo por herramienta|
|**Búsqueda de Correos**|Plataformas comerciales OSINT exitosas|Herramientas públicas sin resultados|
|**Dorks y Archivos Ocultos**|Sí (Google, Wayback, robots.txt)|No implementado / Omitido|
|**Huella Tecnológica**|Dependencia de GUI web (Netcraft)|Extracción nativa masiva (WhatWeb)|
|**Gestión de Errores**|Requiere adaptación manual del analista|Reintentos y desvíos automatizados|

---
---
### Errores de ejecución y bloqueos de herramientas

Durante su ejecución, el agente automatizado se topó con varias limitaciones técnicas y bloqueos que quedaron registrados en sus trazas:

- **Bloqueo anti-bots:** La herramienta `huella_netcraft` falló al intentar analizar el dominio, ya que el servicio bloqueó al cliente automatizado al requerir JavaScript, devolviendo una página sin datos.

- **Fallos de resolución HTTP:** La herramienta `tecnologias_whatweb` no logró devolver resultados para subdominios clave como `chat.snapchat.com`, `blog.snapchat.com` y `advertising.snapchat.com`.

- **Inestabilidad de servicios externos:** En su primer intento, la consulta a `crt.sh` devolvió un error "HTTP Error 502: Bad Gateway". Aunque más tarde logró recuperar datos, esto demuestra dependencia de la estabilidad de la API.

- **Fracaso en la recolección de correos:** La herramienta `correos_theharvester` falló en su primer intento sin dar detalles de error. En su segundo intento logró ejecutarse, pero fue incapaz de encontrar un solo correo electrónico válido.
### Puntos ciegos y omisiones estratégicas (Lo que no buscó)

A diferencia de mi análisis manual, el agente de IA se limitó a un reconocimiento de infraestructura puro, perdiendo información valiosa a nivel de OSINT y lógica de negocio:

- **Ficheros sensibles y políticas:** El agente no buscó ni analizó archivos expuestos comunes como `robots.txt` (que reveló rutas y sitemaps en tu análisis) o `.well-known/security.txt` (que reveló programas de Bug Bounty en HackerOne).
    
- **Histórico web:** El agente no utilizó la Wayback Machine, perdiendo la oportunidad de descubrir endpoints JSON históricos (`ai-plugin.json`, `assetlinks.json`).
    
- **Escaneo de puertos y servicios (Shodan):** Mientras que yo utilize InternetDB/Shodan para descubrir que ciertas IPs correspondían a balanceadores de carga, Nginx y sistemas LMS (Workramp), el agente no realizó ningún cruce de IPs con bases de datos de puertos abiertos.
    
- **WHOIS Inverso de IPs:** El agente solo hizo WHOIS al dominio principal (`snapchat.com`). Yo iteré sobre las IPs de los subdominios para hacer WHOIS, descubriendo qué infraestructura dependía de Amazon, Salesforce o Zendesk.
    
- **Búsquedas de evasión (Google Dorks):** El agente no ejecutó operadores de búsqueda avanzada en buscadores tradicionales para buscar documentos ofimáticos, credenciales o paneles expuestos.
    
- **Inteligencia de Fuentes Abiertas para identidades:** Al fallar con theHarvester, el agente se rindió en la búsqueda de correos. No fue capaz de pivotar hacia plataformas de terceros (como Hunter.io o RocketReach) para identificar el formato de los correos corporativos.

---
---
### 1. Lo que hizo mejor el agente vs. lo que hiciste mejor yo

**El agente destacó en velocidad, concurrencia y recolección técnica masiva.**

- **Estructuración técnica:** Ejecutó un mapeo veloz de la infraestructura web, utilizando `whatweb` para listar frameworks (Next.js, Express) y extraer cabeceras de seguridad complejas (HSTS, CSP, X-Frame-Options).

- **Capacidad de procesamiento:** Fue capaz de procesar cientos de dominios en segundos, extrayendo los DNS y agrupando 29 registros TXT sin intervención. Entregó el resultado en un formato ejecutivo, tabular y directo.

**Yo destaque en pensamiento lateral, OSINT y adaptabilidad.**

- **Pivotar ante obstáculos:** Cuando no tenía correos, salí del flujo técnico y busque en plataformas comerciales como Hunter.io y RocketReach para entender la lógica de negocio de la empresa.

- **Búsqueda de configuraciones humanas:** Entendí que los administradores cometen errores. Por eso busqué en el histórico de Wayback Machine descubriendo archivos JSON filtrados (`ai-plugin.json`), revisé el `robots.txt` y ejecuté Google Dorks.

- **Profundización en infraestructura:** No me quedé en el WHOIS del dominio principal; iteré sobre las IPs de los subdominios para descubrir mediante WHOIS inverso redes subyacentes de Amazon, Salesforce y Zendesk, y usé Shodan para detectar balanceadores de carga y plataformas LMS.

### 2. Por qué falló el agente

Los errores del agente no se deben a que "piense mal", sino a la rigidez de su diseño y a la falta de herramientas para ejecutar pensamiento lateral:

- **Mecanismos Anti-Bot y fallos de API:** Falló en Netcraft porque la página requiere renderizado de JavaScript o detecta clientes automatizados (bots), devolviendo una página vacía. También sufrió un timeout HTTP 502 al consultar `crt.sh`, un problema habitual de estabilidad en esa API.
### 3. Confianza y revisión del informe

El mayor peligro de las IAs en el reconocimiento es la falsa sensación de cobertura total.
Siempre se debe comprobar:

- **Falsos negativos en los logs:** Revisar la traza de ejecución (`traza.jsonl.md`) para detectar qué herramientas fallaron silenciosamente. Por ejemplo, el informe final dice "0 correos" como un hecho, pero los logs revelan que `theHarvester` falló en su primer intento. Esto significa que el dato no es concluyente, sino producto de un fallo técnico.

- **Dominios omitidos por error de red:** Hay que cruzar la lista de subdominios descubiertos con los resultados de las herramientas. El agente omitió detalles de subdominios clave como `advertising.snapchat.com` porque la herramienta `whatweb` no devolvió resultados en ese momento.

- **La cobertura OSINT:** Es obligatorio asumir que el agente no ha cubierto fugas de información, repositorios de código, redes sociales, Dorks, ni archivos ocultos. Toda la inteligencia de fuentes abiertas que requiere correlación humana (como buscar el formato del correo de un empleado) debe añadirse manualmente al proceso.

El agente es un excelente asistente para automatizar el descubrimiento de la superficie técnica expuesta en los primeros 5 minutos de un _pentest_, pero el análisis crítico de esos datos siempre requiere el contexto de un auditor humano.
