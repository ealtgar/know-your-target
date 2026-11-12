bloqueado whois_dominio(dominio='snap.com')
bloqueado dns_registros(dominio='snap.com')


## Informe de Reconocimiento Pasivo

### Alcance autorizado

Solo **snapchat.com** (y sus subdominios listados en el alcance) están dentro del ámbito autorizado. **shopify.com** y **decathlon.es** **no están en la lista de alcance** y por tanto no han sido investigados.

---

## snapchat.com

### 1. Registro WHOIS (whois_dominio)

| Campo | Valor |
|-------|-------|
| Dominio | SNAPCHAT.COM |
| Fecha de alta | 2012-02-28 |
| Fecha de caducidad | 2034-02-28 |
| Último cambio | 2026-01-28 |
| Registrar | 292 |
| Estado | client/server delete, transfer y update prohibited |
| Nameservers | NS-1468.AWSDNS-55.ORG, NS-1892.AWSDNS-44.CO.UK, NS-220.AWSDNS-27.COM, NS-530.AWSDNS-02.NET |

### 2. Registros DNS (dns_registros)

| Tipo | Valor | Herramienta |
|------|-------|-------------|
| **A** | `34.149.46.130` | dns_registros |
| **AAAA** | Sin registros | dns_registros |
| **NS** | `ns-220.awsdns-27.com`, `ns-1468.awsdns-55.org`, `ns-530.awsdns-02.net`, `ns-1892.awsdns-44.co.uk` | dns_registros |
| **MX** | `10 aspmx.l.google.com`, `20 alt1.aspmx.l.google.com`, `30 alt2.aspmx.l.google.com`, `40 aspmx2.googlemail.com`, `50 aspmx3.googlemail.com` | dns_registros |
| **SOA** | `ns-220.awsdns-27.com` / `awsdns-hostmaster.amazon.com` / serial 1 / refresh 7200 / retry 900 / expire 1209600 / minimum 86400 | dns_registros |
| **TXT** | Múltiples registros de verificación (Google, Atlassian, Adobe, Shopify, Apple, Microsoft, Canva, Miro, HubSpot, etc.) y SPF: `v=spf1 include:_spf.google.com include:mail.zendesk.com include:aspmx.pardot.com -all` | dns_registros |

**Observaciones DNS:**
- La IP `34.149.46.130` pertenece a **Google Cloud** (GCP).
- Los nameservers son de **AWS Route 53**.
- El correo se gestiona con **Google Workspace** ( MX apuntan a Google) y **Pardot/Zendesk**.
- El registro TXT de Shopify (`shopify-verification-code=6AbSmjYHNX0fOCzG0oBfncSsCVJfgT`) confirma integración con Shopify.

### 3. Subdominios (subdominios_subfinder)

Se encontraron **358 subdominios** dentro del alcance autorizado. Los más relevantes incluyen:

| Categoría | Ejemplos |
|-----------|----------|
| API | `api.snapchat.com`, `aws.api.snapchat.com`, `gcp.api.snapchat.com`, `bitmoji.api.snapchat.com` |
| Ads/Marketing | `ads.snapchat.com`, `adsapi.snapchat.com`, `advertising.snapchat.com`, `ad-center.snapchat.com` |
| App | `app.snapchat.com`, `app-analytics.snapchat.com`, `app-analytics2.snapchat.com` |
| Chat | `chat.snapchat.com`, `chat-gateway-prod.chat.snapchat.com` |
| Lens/Creatividad | `lens.snapchat.com`, `lensstudio.snapchat.com`, `lenswebbuilder.snapchat.com` |
| Mail | `o1.mail.snapchat.com` … `o18.mail.n.snapchat.com` (Múltiples MX/relay) |
| Business | `business.snapchat.com`, `business-manager.snapchat.com`, `businesshelp.snapchat.com` |
| Developer | `developer.snapchat.com`, `developers.snapchat.com` |
| Gateway | `gateway.snapchat.com`, `us-east1-aws.gateway.snapchat.com`, `eu-west1-aws.gateway.snapchat.com` |
| Cognac/GS | Múltiples bajo `*.gs.*.cognac.snapchat.com` (us-central1, europe-west2, asia-southeast1) |
| Publisher | `snappublisher.snapchat.com` y subdominios `_cisco-uds`, `_dmarc`, `_mta-sts`, etc. |

*(Herramienta: subdominios_subfinder con todas_las_fuentes=True)*

### 4. Tecnologías web (tecnologias_whatweb)

| Dominio | Status | IP | Tecnologías detectadas |
|---------|--------|----|------------------------|
| `snapchat.com` | 301 Redirect | `34.149.46.130` | Redirige a `https://www.snapchat.com` |
| `www.snapchat.com` | 200 OK | `34.149.46.130` | **HTTPServer: API Gateway**, **X-Powered-By: Next.js**, Open-Graph, Strict-Transport-Security, X-Frame-Options: SAMEORIGIN, Permissions-Policy, Content-Security-Policy, cookies `sc-config-cache-key` y `sc-wcid`, Via-Proxy: `1.1 google` |
| `api.snapchat.com` | 404 Not Found | `142.251.142.148` | Google infrastructure |

### 5. Hosts adicionales (correos_theharvester)

Se obtuvieron **62 hosts** adicionales (sin correos electrónicos directos):
- Incluye múltiples subdominios de API (`aws-acc.api.snapchat.com`, `gcp.api.snapchat.com`, `staging-gcp.api.snapchat.com`)
- Mail relays (`o1.mail.snapchat.com` a `o18.mail.n.snapchat.com`)
- Learn/Ads (`click.learn.ads.snapchat.com`, `image.learn.ads.snapchat.com`, `view.learn.ads.snapchat.com`)
- Staging environments (`staging-gcp.api.snapchat.com`, `staging.app-analytics.snapchat.com`)

### 6. Herramientas que fallaron

| Herramienta | Estado |
|-------------|--------|
| subdominios_crtsh | ERROR 502 Bad Gateway (crt.sh inestable) |
| huella_netcraft | Página sin datos (requiere JS o bloquea scraping) |
| correos_theharvester (fuentes completas) | Falló en primer intento; reintentado con fuentes reducidas (éxito) |

---

## shopify.com y decathlon.es

Ambos dominios **no están dentro del alcance autorizado** definido para esta auditoría. Por lo tanto, no se han investigado. El alcance cubre exclusivamente `snapchat.com` y sus subdominios listados, además de algunos dominios relacionados (`snap.com`, `snapmap.com`, `snapstore.com`, `yellowla.com`, etc.).

Si necesitas investigación sobre shopify.com o decathlon.es, sería necesario ampliar el alcance autorizado.

Tokens: {'entrada': 46357, 'salida': 4894}
