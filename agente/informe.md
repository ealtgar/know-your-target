## Informe de Reconocimiento Pasivo: snapchat.com

---

### 1. Registro WHOIS

| Campo | Valor | Herramienta |
|-------|-------|-------------|
| Dominio | SNAPCHAT.COM | `whois_dominio` |
| Fecha de registro | 2012-02-28 | `whois_dominio` |
| Fecha de expiración | 2034-02-28 | `whois_dominio` |
| Última actualización | 2026-01-28 | `whois_dominio` |
| Registrador | Entidad 292 (GoDaddy) | `whois_dominio` |
| Estado | client delete/transfer/update prohibited, server delete/transfer/update prohibited | `whois_dominio` |
| Nameservers | ns-1468.awsdns-55.org, ns-1892.awsdns-44.co.uk, ns-220.awsdns-27.com, ns-530.awsdns-02.net | `whois_dominio` |

---

### 2. Registros DNS Principales

#### A
- `snapchat.com` → `34.149.46.130` (`dns_registros`)

#### AAAA
- Sin registros IPv6 para `snapchat.com` (`dns_registros`)

#### MX
- `10 aspmx.l.google.com.`
- `20 alt1.aspmx.l.google.com.`
- `30 alt2.aspmx.l.google.com.`
- `40 aspmx2.googlemail.com.`
- `50 aspmx3.googlemail.com.`
- (`dns_registros`)

#### NS
- `ns-1468.awsdns-55.org.`
- `ns-1892.awsdns-44.co.uk.`
- `ns-220.awsdns-27.com.`
- `ns-530.awsdns-02.net.`
- (`dns_registros`)

#### SOA
- `ns-220.awsdns-27.com. awsdns-hostmaster.amazon.com. 1 7200 900 1209600 86400` (`dns_registros`)

#### TXT (destacados)
- SPF: `v=spf1 include:_spf.google.com include:mail.zendesk.com include:aspmx.pardot.com -all`
- Verificaciones de dominio: Google (5 registros), Apple, Microsoft, Dropbox, Atlassian (3), Adobe, OneTrust (2), Yahoo (3), OpenAI, Anthropic, Shopify, HubSpot, Miro, Docker, Segment, JAMF, Autodesk, Canva, Linear, LogMeIn, TailScale, Censys, Smartsheet, Krea, Arcules, Parallels, Snap, Sonatype, Pardot
- (`dns_registros`)

---

### 3. Subdominios en Alcance

#### crt.sh (transparencia de certificados)
- **221 subdominios** dentro del alcance autorizado (`subdominios_crtsh`)

#### subfinder (fuentes públicas)
- **264 subdominios** dentro del alcance autorizado (`subdominios_subfinder`)

#### theHarvester (hosts)
- **155 hosts** dentro del alcance (`correos_theharvester`)
- **0 correos electrónicos** encontrados (`correos_theharvester`)

---

### 4. DNS de Subdominios Clave

| Subdominio | Registro A/CNAME | Herramienta |
|------------|------------------|-------------|
| `www.snapchat.com` | `34.149.46.130` (CNAME: `web-gcp.api.snapchat.com.` → `web-gcp.api.sc-gw.com.`) | `dns_registros` |
| `api.snapchat.com` | `142.251.142.148` (CNAME: `feelinsonice-hrd.appspot.com.`) | `dns_registros` |
| `app.snapchat.com` | `34.149.130.113` (CNAME: `app-snapchat.snapchat.com.`) | `dns_registros` |
| `ads.snapchat.com` | `34.149.46.130` (CNAME: `web-gcp.api.snapchat.com.` → `web-gcp.api.sc-gw.com.`) | `dns_registros` |
| `chat.snapchat.com` | Sin registros A | `dns_registros` |
| `developer.snapchat.com` | `34.120.54.238` | `dns_registros` |
| `store.snapchat.com` | `108.177.15.121` (CNAME: `ghs.googlehosted.com.`) | `dns_registros` |
| `investors.snapchat.com` | `34.120.54.238` | `dns_registros` |
| `creators.snapchat.com` | `34.120.54.238` | `dns_registros` |
| `advertising.snapchat.com` | `108.177.15.121` (CNAME: `ghs.googlehosted.com.`) | `dns_registros` |
| `business.snapchat.com` | `34.149.46.130` (CNAME: `web-gcp.api.snapchat.com.` → `web-gcp.api.sc-gw.com.`) | `dns_registros` |
| `lens.snapchat.com` | `99.84.9.121, 99.84.9.125, 99.84.9.64, 99.84.9.49` (CNAME: `d19f6ujxq26e2c.cloudfront.net.`) | `dns_registros` |
| `auth.snapchat.com` | `108.177.15.121` (CNAME: `ghs.googlehosted.com.`) | `dns_registros` |
| `search.snapchat.com` | `108.177.15.121` (CNAME: `ghs.googlehosted.com.`) | `dns_registros` |
| `snappublisher.snapchat.com` | `108.177.15.121` (CNAME: `ghs.googlehosted.com.`) | `dns_registros` |
| `gateway.snapchat.com` | Sin registros A | `dns_registros` |
| `blog.snapchat.com` | Sin registros A | `dns_registros` |
| `profiles.snapchat.com` | Sin registros A | `dns_registros` |

---

### 5. Huella Tecnológica

| Dominio | Tecnologías Detectadas | Herramienta |
|---------|------------------------|-------------|
| `www.snapchat.com` | **Servidor**: API Gateway, **Framework**: Next.js, **CDN/Proxy**: Google (Via: 1.1 google), **Seguridad**: HSTS (31536000s, includeSubDomains), X-Frame-Options: SAMEORIGIN, CSP, Referrer-Policy, Permissions-Policy, X-Content-Type-Options, **Cookies**: sc-config-cache-key, sc-wcid, **Powered-By**: Snap, **OpenGraph**: website | `tecnologias_whatweb` |
| `api.snapchat.com` | **Servidor**: Google Frontend, **IP**: 142.251.142.148, **Proxy**: Google, **Respuesta**: 404 Not Found | `tecnologias_whatweb` |
| `app.snapchat.com` | **Servidor**: Google Frontend, **IP**: 34.149.130.113, **Headers**: x-snapchat-request-id, x-snapchat-notice, x-cloud-trace-context, **Proxy**: Google | `tecnologias_whatweb` |
| `ads.snapchat.com` | **Servidor**: API Gateway, **IP**: 34.149.46.130, **Seguridad**: HSTS (31536000s, includeSubDomains), CSP, X-Frame-Options: SAMEORIGIN, X-Content-Type-Options, Referrer-Policy, Permissions-Policy, Cross-Origin policies, **Proxy**: Google (doble salto), **Headers**: reporting-endpoints, x-envoy-upstream-service-time | `tecnologias_whatweb` |
| `developer.snapchat.com` | **Servidor**: Google Frontend, **Framework**: Express, **IP**: 34.120.54.238, **Proxy**: Google, **Redirección**: 308 → developers.snap.com | `tecnologias_whatweb` |
| `store.snapchat.com` | **Servidor**: Google Frontend, **IP**: 108.177.15.121, **Seguridad**: HSTS (31536000s, includeSubdomains), X-Frame-Options: DENY, X-XSS-Protection: 1; mode=block, CSP, X-Content-Type-Options | `tecnologias_whatweb` |
| `creators.snapchat.com` | **Servidor**: Google Frontend, **IP**: 34.120.54.238, **Seguridad**: HSTS (31536000s, includeSubDomains, preload), X-Frame-Options: DENY, CSP, Referrer-Policy, Permissions-Policy, X-Content-Type-Options, **OpenGraph**: website | `tecnologias_whatweb` |
| `lens.snapchat.com` | **Servidor**: CloudFront (Amazon), **CDN**: Amazon CloudFront, **IP**: 99.84.9.64, **Proxy**: CloudFront, **Redirección**: 301 → www.snapchat.com/lens | `tecnologias_whatweb` |

---

### 6. Infraestructura Detectada

| Componente | Detalle |
|------------|---------|
| **DNS** | AWS Route 53 (nameservers awsdns-*) |
| **Hosting principal** | Google Cloud Platform (IPs 34.149.x.x, 34.120.x.x) |
| **CDN** | Google Cloud CDN / Proxy + Amazon CloudFront (lens.snapchat.com) |
| **Correo** | Google Workspace (MX: aspmx.l.google.com) |
| **Framework web** | Next.js (www.snapchat.com), Express (developer.snapchat.com) |
| **Gateway API** | API Gateway con Envoy proxy (x-envoy-upstream-service-time) |
| **App Engine** | App Engine para api.snapchat.com (feelinsonice-hrd.appspot.com) |
| **Google Hosted** | Múltiples subdominios en Google Hosted (ghs.googlehosted.com) |

---

### 7. Resumen

- **Dominio principal**: snapchat.com, registrado en 2012, expira en 2034
- **DNS**: Gestionado por AWS Route 53 con 4 nameservers globales
- **Correo**: Google Workspace con SPF incluyendo Google, Zendesk y Pardot
- **Subdominios identificados**: 221-264 subdominios en alcance según fuente
- **Infraestructura**: Híbrida entre Google Cloud (principal) y AWS (DNS), con CloudFront para algunos servicios específicos
- **Seguridad**: HSTS con preload en varios subdominios, CSP configurado, protección XSS
- **Tecnologías**: Next.js, Express, API Gateway con Envoy, Google Frontend/Proxy, Amazon CloudFront
