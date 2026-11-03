# 1. Definición del Alcance (Scope)

El presente documento define los límites operativos, los activos autorizados y las restricciones para la evaluación de seguridad (Hacking Ético) realizada sobre la infraestructura de **Snapchat (Snap Inc.)**.

Este alcance debe ser respetado estrictamente durante todas las fases de la auditoría (reconocimiento pasivo, reconocimiento activo y explotación).
## 1.1. Activos Autorizados (In-Scope)

La evaluación se centra en la infraestructura principal de la organización y sus subdominios asociados. El listado exhaustivo y oficial de los activos que entran dentro del alcance de esta auditoría se encuentra detallado en el siguiente documento adjunto proporcionado por la organización/plataforma de Bug Bounty:

- **Documento de referencia:** `scopes_for_snapchat_at_2026-11-02_16_48_53_UTC.csv`

Cualquier subdominio o dirección IP que se derive de `snapchat.com` y esté presente en dicho documento, se considera un objetivo válido para las pruebas, salvo que coincida con las exclusiones explícitas.
## 1.2. Activos Excluidos (Out-of-Scope)

Queda terminantemente prohibido realizar cualquier tipo de escaneo activo, enumeración intrusiva o intento de explotación sobre los siguientes activos, ya que han sido marcados explícitamente como fuera de alcance:

- `support.snapchat.com` (Infraestructura de soporte operada por terceros/Zendesk)
- `returns.spectacles.com`
- `dev.*.playcanvas.com` (Cualquier variación de subdominio de desarrollo en playcanvas)
- `dev.playcanv.as`

_Nota:_ Si durante la fase de reconocimiento se identifica que un subdominio válido apunta a un servicio de terceros (SaaS, CDN, Cloud Provider) cuyas políticas de uso prohíben el escaneo (ej. portales de atención al cliente de Zendesk), las pruebas deberán limitarse exclusivamente a las configuraciones gestionadas por Snap Inc., evitando afectar la infraestructura del proveedor.

## 1.3. Reglas de Interacción (Rules of Engagement)

Para garantizar la integridad y disponibilidad de los servicios de la organización durante la auditoría, se establecen las siguientes directrices:

1. **Ataques de Denegación de Servicio (DoS/DDoS):** Están estrictamente prohibidos.
2. **Ingeniería Social:** Las pruebas de phishing, spear-phishing o manipulación de personal se limitarán a la obtención de métricas y apertura de correos, sin solicitar credenciales reales ni ejecutar _malware_ en los equipos de los empleados.
3. **Explotación Destructiva:** No se permite la alteración, borrado o exfiltración masiva de datos (PII o datos confidenciales) en caso de comprometer un sistema. Se deberá utilizar una Prueba de Concepto (PoC) inofensiva para demostrar el impacto (por ejemplo, lectura del archivo `/etc/passwd` o ejecución de un `whoami`).