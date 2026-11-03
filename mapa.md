# Resumen

**Snapchat (Snap Inc.)** es una empresa tecnológica global de mensajería y redes sociales cuya infraestructura expuesta se aloja de forma masiva en entornos en la nube como AWS y Google Cloud, bajo la protección de redes de distribución de contenido y balanceadores de carga.

El reconocimiento pasivo ha identificado una superficie de ataque de 298 subdominios, vinculados a múltiples integraciones de terceros empresariales como Zendesk, Salesforce y Workramp. A nivel de red, la exposición externa se reduce estrictamente a los puertos web estándar 80 y 443, y su archivo `security.txt` público redirige formalmente a un programa de recompensas por vulnerabilidades gestionado a través de HackerOne.

Aunque no se han detectado fugas de información sensible mediante Google Dorks, la recolección de inteligencia de código abierto ha permitido perfilar a los empleados y correos corporativos, estableciendo las bases para posibles simulaciones de ingeniería social (en nuestro caso de *bug bounty* no estamos permitidos).

---
# Dominios y subdominios

A partir de la enumeración realizada con herramientas como `subfinder`, y consultas a `crt.sh` o `DNSDumpster`, se aislaron 298 subdominios únicos tras el filtrado de duplicados. A continuación, se detallan los activos más relevantes analizados, junto con las exclusiones explícitas identificadas:

| **Subdominio / Dominio**                   | **Dirección IP**                                  | **En Alcance** | **Propósito Aparente**                                                                                 |
| :----------------------------------------- | ------------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------ |
| `snapchat.com`                             | `34.149.46.130`                                   | Sí             | Dominio principal de la organización (Registro A).                                                     |
| `aws.duplex.snapchat.com`                  | `108.128.225.61`                                  | Sí             | Infraestructura en la nube alojada en Amazon Web Services (Instancia EC2) operando por el puerto 443.  |
| `cloud.email.snapchat.com`                 | `128.245.136.249`                                 | Sí             | Plataforma de gestión y envío de correos electrónicos operada por Salesforce.                          |
| `focus.snapchat.com`                       | `54.241.238.63`<br><br>  <br><br>`13.56.100.93`   | Sí             | Sistema de Gestión de Aprendizaje (LMS - Workramp) operando detrás de un balanceador de carga y Nginx. |
| `help.snapchat.com`                        | `216.198.54.11`                                   | Sí             | Centro de ayuda e infraestructura de atención al usuario operada por Zendesk.                          |
| `image.email.snapchat.com`                 | `13.224.83.54`<br><br>  <br><br>_(y otras 3 IPs)_ | Sí             | Alojamiento de imágenes para campañas de correo, protegido por el CDN Amazon CloudFront.               |
| `support.snapchat.com`                     | _No aplicable_                                    | No             | Excluido explícitamente del alcance según la configuración de los escaneos.                            |
| `returns.spectacles.com`                   | _No aplicable_                                    | No             | Excluido explícitamente del alcance de las pruebas.                                                    |
| `dev.*.playcanvas.com` / `dev.playcanv.as` | _No aplicable_                                    | No             | Subdominios excluidos explícitamente del alcance.                                                      |

---
# Hosting y Servicios en la Nube

- La infraestructura principal está fuertemente apoyada en Amazon Web Services (AWS), utilizando instancias EC2 (ej. `aws.duplex.snapchat.com`), balanceadores de carga elásticos (ej. `focus.snapchat.com`) y redes de distribución de contenido (CDN) como Amazon CloudFront (ej. `image.email.snapchat.com`).

- El servicio de resolución de nombres de dominio (DNS) está delegado a la infraestructura de AWS, utilizando servidores como `ns-1468.awsdns-55.org`.

- Se identifica una fuerte dependencia de plataformas en la nube de terceros para operaciones empresariales y soporte, alojadas en infraestructuras de Salesforce (ej. `cloud.email.snapchat.com`) y Zendesk (ej. `help.snapchat.com`).
### Infraestructura de Correo Electrónico

- Los registros DNS tipo MX apuntan directamente a servidores de Google (`aspmx.l.google.com`, entre otros), lo que confirma el uso de Google Workspace para la gestión y recepción de correo corporativo.

- El registro SPF (`v=spf1 include:_spf.google.com include:mail.zendesk.com include:aspmx.pardot.com -all`) revela y autoriza el envío de correos legítimos en nombre de la organización a través de Google, Zendesk y la plataforma de automatización de marketing Pardot.
### Tecnologías identificadas

- El análisis de los registros TXT de verificación de dominio expone la integración con múltiples soluciones SaaS y tecnológicas, incluyendo Atlassian, HubSpot, OneTrust, Docker, Jamf, Adobe, OpenAI, Anthropic, Shopify, Canva, Dropbox y Tailscale.

- A nivel de servidor web, se ha detectado el uso de Nginx operando detrás de los balanceadores de carga. Además, utilizan la plataforma Workramp como su Sistema de Gestión de Aprendizaje (LMS).
### Resultados de Shodan (Servicios expuestos)

- **108.128.225.61 (`aws.duplex.snapchat.com`):** Identificada como una instancia EC2 de AWS con el puerto 443 (HTTPS) expuesto.

- **13.224.83.54 (`image.email.snapchat.com`):** Nodo de la CDN Amazon CloudFront con los puertos web estándar 80 y 443 expuestos.

- **54.241.238.63 (`focus.snapchat.com`):** Servidor detrás de un balanceador de carga de AWS ejecutando Nginx para el LMS Workramp, exponiendo únicamente los puertos 80 y 443. En ninguna de las muestras analizadas se identificaron puertos de administración (SSH, RDP, FTP) expuestos al exterior.

---
# Correos y personas
### Patrón de Correo Electrónico y Perfilado de empleados

- Durante la fase de reconocimiento pasivo en los activos analizados y motores de búsqueda, no se logró recolectar ninguna dirección de correo electrónico legítima perteneciente a los empleados directamente desde su infraestructura.

- Para solventar esta limitación, la investigación se apoyó en plataformas OSINT (Inteligencia de Fuentes Abiertas) como Hunter.io y RocketReach, con el objetivo de identificar a los trabajadores clave de la empresa e inferir la estructura o patrón de sus correos corporativos.

- Una vez obtenidos e inferidos estos correos electrónicos, se emplearon herramientas de inteligencia avanzada como **Epieos** para buscar información adicional, verificando la existencia de cuentas asociadas en diversos servicios web, plataformas colaborativas y redes sociales para ampliar la huella digital del objetivo.

- Adicionalmente, las direcciones recolectadas fueron contrastadas contra bases de datos de brechas de seguridad utilizando **Have I Been Pwned** (HIBP). Este análisis confirmó que algunos de los correos corporativos han sido expuestos en filtraciones de datos de terceros, lo que incrementa significativamente el riesgo de ataques basados en la reutilización de contraseñas (_Credential Stuffing_) y facilita la creación de pretextos para campañas de _Spear-Phishing_.
##### Patrón de correo corporativo

```
[inicial_nombre][apellido]@snapchat.com
```
### Información Organizacional y de Contacto

- La información pública de los registros WHOIS expone que la protección y gestión de los dominios corporativos está delegada en Markmonitor Inc. y DNStination Inc.

- Se ha identificado una dirección física corporativa vinculada a los registros en _3450 Sacramento Street Suite 405 San Francisco, CA, 94118 US_.

- Se recuperaron datos de contacto técnico y de abusos, incluyendo el correo electrónico `admin@dnstination.com` y las líneas telefónicas directas `+1.4155319335` y `+1.2086851750`.

---
# Puntos de interés
### 1. Plataforma de Aprendizaje (LMS) en `focus.snapchat.com`

Este subdominio aloja *Workramp* (un Sistema de Gestión de Aprendizaje) operando tras un balanceador de carga y Nginx. Los portales internos o plataformas satélite gestionadas por terceros suelen tener una superficie de exposición menos monitorizada que la aplicación principal. En la fase activa, es clave interactuar con este servicio para buscar vulnerabilidades en la integración del inicio de sesión único (SSO), fallos de autorización (Broken Access Control) o fugas de datos mediante la enumeración de usuarios.

### 2. Integraciones de terceros y Endpoints ocultos

El histórico web reveló archivos interesantes como `/.well-known/ai-plugin.json`, y los registros TXT de DNS exponen una dependencia masiva de servicios SaaS (OpenAI, Atlassian, HubSpot, Jamf, Docker). En la fase activa, se debe realizar un _fuzzing_ intensivo de directorios y APIs en los subdominios descubiertos basándose en estos hallazgos para detectar posibles IDOR, SSRF o la exposición de tokens y claves de API (API Keys) mal configuradas.


### 3. Superficie de autenticación del personal (Identity Attacks)

Al haber confirmado previamente que existen correos corporativos expuestos en brechas de seguridad (HIBP) y contar con una huella digital enriquecida, el enfoque activo debe dirigirse al factor humano e identitario. Esto implica localizar paneles de inicio de sesión (como el LMS o los accesos de Zendesk en `help.snapchat.com`) para realizar simulaciones de _Password Spraying_ o _Credential Stuffing_ con las contraseñas filtradas, además de estructurar campañas de _Spear-Phishing_ (en caso de que estas técnicas estén dentro del Scope).