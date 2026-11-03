# DNS
## Whois
#### Contact Information
##### Abuse Contact
- Name: **Markmonitor Inc.**
- Phone: `+1.2086851750`
##### Registrant Contact
- Organization: **DNStination Inc.**
- Address: *3450 Sacramento Street Suite 405 San Francisco, CA, 94118 US*
- Phone: `+1.4155319335`
- Email: `admin [at] dnstination [dot] com`
##### Tech Contact
- Phone: `1+4155319335`
- Email: `admin [at] dnstination [dot] com`
#### Registrar Information
- Registrar: MarkMonitor Inc.
- WHOIS Server: `whois.markmonitor.com`
- Referral URL: http://www.markmonitor.com
#### Important Dates
- Created: 28/02/2012
- Updated: 28/01/2026
- Expires: 28/02/2034
#### Nameservers

|         Hostname          | IP Address        |
| :-----------------------: | ----------------- |
|  `ns-1468.awsdns-55.org`  | `205.251.197.188` |
| `ns-1892.awsdns-44.co.uk` | `205.251.199.100` |
|  `ns-220.awsdns-27.com`   | `205.251.192.220` |
|  `ns-530.awsdns-02.net`   | `205.251.194.18`  |

---
## Registros DNS
#### DNSDumpster

```bash
curl -s -H "X-API-KEY: [api-key de crt.sh]" "https://api.dnsdumpster.com/domain/snapchat.com" | jq > dns_records.json
```
#### `dig`

```bash
# IPv4
dig +short snapchat.com
34.149.46.130

# IPv6
dig +short aaaa snapchat.com
- No encontrado -
  
# CNAME
dig +short cname snapchat.com
- No encontrado -

# Servernames
dig +short ns snapchat.com
ns-1892.awsdns-44.co.uk.
ns-530.awsdns-02.net.
ns-220.awsdns-27.com.
ns-1468.awsdns-55.org.

# Servidores de correo
dig +short mx snapchat.com
40 aspmx2.googlemail.com.
50 aspmx3.googlemail.com.
20 alt1.aspmx.l.google.com.
10 aspmx.l.google.com.
30 alt2.aspmx.l.google.com.

# SOA
dig +short soa snapchat.com
ns-220.awsdns-27.com. awsdns-hostmaster.amazon.com. 1 7200 900 1209600 86400

# Registros TXT
dig +short txt snapchat.com
"arcules-domain-verification=kEVxs7LUGURYpDYCelXSgp02wBuL6A82zKQMMw8lGzR"
"google-site-verification=Eo-pwhENGkrh6E74BafjjhjK4dGk0B1Tv12bUn5UPSY"
"onetrust-domain-verification=faca66624bfe477db467f97c7583b7ba"
"google-site-verification=Ro2UVvcjx7U_bRc-_HAUELMOxwk4Y6n5FX9FQt8BDsQ"
"docker-verification=2351a4bf-bc17-42ff-8fca-521e86376280"
"yahoo-verification-key=hbsSgAjgGym9aXgBQSAX5APr5RKaTlmtGlqFTCMIEXo="
"apple-domain-verification=hAi0YbrGnN5ny4wm"
"yahoo-verification-key=xUKCyvTR9ya3lyjYFuWPLGfSFLC/5C0y2txg4crwEbw="
"https://issues.sonatype.org/browse/OSSRH-54682"
"smartsheet-site-validation=dw0MifosV2eGg1JG9ZTtiGpSGNuiqybJ"
"atlassian-domain-verification=P7v4/0SuI03V2xsQfPTYYZLbRwBN1QkqBg4E/zqmJVvyWKraMaJRbamwkK2vWrx0"
"google-site-verification=eye-nbnjs2nv4ll-8vo9ijpgkdvyrs8h2j_1bzkp-t0"
"jamf-site-verification=_Y2-z-8UweEkmdMZsNbTJg"
"parallels-domain-verification=58886ce349db42dfbfb94599884a65ead28c9543a5c947df8fc596694c81eba6"
"google-site-verification=tHsCd67KywyjuYvvr7V9I4PFTXXznN48z-jvPm20yBE"
"google-site-verification=bgzZGVgOr4py5YcPQHFZYJFJbarBD_shCxIvjQS1grI"
"logmein-verification-code=fd76bf0c-ec62-4587-bb84-4511579e41f4"
"censys-domain-verification=9U1U43sYXK5eDeoXbt8WB090FMa8IystN7iMx0waR50S"
"segment-site-verification=e6U89hyQcmGvDFTApWYKvbj7NFSMu8zj"
"atlassian-domain-verification=t2mP/OxdJvz/S28h3o/5egOc105U1aKneVRngll9cfhI4Un8gQxYaQjIPVaKpKpT"
"hubspot-developer-verification=Zjk1NTNlNmYtODAxNi00YzNhLTgzNGEtY2JlNWQyNGRhZmFk"
"_hh9zpxhf35itout7v7mwibqktr44s3s"
"onetrust-domain-verification=32eb1654587e494fbd3b4f8a54a6b57f"
"adobe-idp-site-verification=1b7089e1333b1302c4f425ff60baae967ac377d76fb6aa7bb61c9f0282fd664d"
"autodesk-domain-verification=S6bhF0FKFgY957I6SLKW"
"krea-verification=b6d6daff3226c8bdfa48187fc11d00d721aa8ed08878659c1ee40b73104da392"
"miro-verification=b341b9dfb098865b7517b6c662e94e5538603be4"
"anthropic-domain-verification-kg6835=FrP90V31rmTTa7Cu3plqLLMEx"
"linear-domain-verification=v82bwvzkpw5w"
"pardot_346841_*=de35b68dd0e766cfba41cc068f8b424a6ce7ac92052cb30fe9a4a55ac88a0583"
"openai-domain-verification=dv-qRVXfFNUY6fVpEXy5skTuRnd"
"yahoo-verification-key=T1Hbkkgw9crF2nr93/q/Zb+IzUPXWSZEmqh1G5VCds0="
"shopify-verification-code=6AbSmjYHNX0fOCzG0oBfncSsCVJfgT"
"TAILSCALE-bAU9TfNGoz4iD4hioxcp"
"MS=255BA8D56417782169DA12894F5A53521A65F7F2"
"3ae8f0a14f7a4c98a9023fe8947467bd"
"atlassian-domain-verification=TH6BFQJRvZM36e0pNbXcEI/RpTrqBb2JDxzoBsBLa3RajLrpmc6pK6Quau40P7oa"
"nyy2gbb26yz2kntxp7ynycsvql0swn71"
"dropbox-domain-verification=oypu2eeh56yg"
"v=spf1 include:_spf.google.com include:mail.zendesk.com include:aspmx.pardot.com -all"
"snapchat-domain-verification-zx5hhx=Q7zL5FmxwFKyQWOuKc4blSh7k"
"canva-site-verification=blQT_XTqOBtV9rXZPJYTvg"
"_vslgkwtl5nwrcpaotz2gw1t4k13zkwb"
```

---
# Subdominios
#### `subfinder`

```bash
subfinder -d "snapchat.com" -silent > subdominios_subfinder.txt
```

```bash
cat subdominios_subfinder.txt

view.learn.ads.snapchat.com
app.snapchat.com
o9.mail.snapchat.com
thekeysca.snapchat.com
asia-southeast1.gs.airtime.cognac.snapchat.com
mail2.support.snapchat.com
us-central1.gs.bmr.cognac.snapchat.com
us-east-1.content-annotations-service.snapchat.com
o1.mail.snapchat.com
story.snapchat.com
adsapimus.snapchat.com
snap.publish.snapchat.com
bolt-staging.snapchat.com
profiles-api-flex-dev.snapchat.com
server-analytics.snapchat.com
click.learn.ads.snapchat.com
groove.snapchat.com
support.lensstudio.snapchat.com
ml.snapchat.com
<snip>
```
#### *crt.sh*

```bash
curl -s "https://crt.sh/?q=%25.snapchat.com&output=json" | jq > crt.sh_results.json

wc -l crt.sh_results.json
32870 crt.sh_results.json
```

```bash
jq -r '.[] | .common_name' crt.sh_results.json | sort | uniq > subdominios_crt.txt
```

```bash
cat subdominios_crt.txt

perception-staging.snapchat.com
app-analytics2.snapchat.com
scan.snapchat.com
businesshelp.snapchat.com
aws.duplex.snapchat.com
lens.snapchat.com
support.lensstudio.snapchat.com
o15.mail.m.snapchat.com
publish.snapchat.com
view.learn.ads.snapchat.com
staging-gcp.api.snapchat.com
mvm-20240424.snapchat.com
static.snapchat.com
topic-sticker-vending-us-east-1.snapchat.com
us-central1.gs.catsr.cognac.snapchat.com
less.snapchat.com
subscriptions.snapchat.com
scan-partners.snapchat.com
chat-internal.snapchat.com
art.snapchat.com
<snip>
```
##### Exclusiones

```bash
grep -E '^support\.snapchat\.com$|^returns\.spectacles\.com$|^dev.*\.playcanvas\.com$|^dev\.playcanv\.as$' subdominios_subfinder.txt

support.snapchat.com
```

```bash
grep -E '^support\.snapchat\.com$|^returns\.spectacles\.com$|^dev.*\.playcanvas\.com$|^dev\.playcanv\.as$' subdominios_crt.txt

support.snapchat.com
```

En ambas listas tan solo existe un subdominio que se encuentra fuera del alcance. Procedemos a eliminarlo:

```bash
vim subdominios_subfinder.txt
vim subdominios_crt.txt
```

---
# Resolver y Mirar la IP

>```bash
>dig +short www.objetivo.es
>whois $IP | grep -iE 'orgname|netname|country'
>```

>[!important]
>Como tenía dos archivos con subdominios (uno de *crt.sh* y el otro de `subfinder`) he decidido moverlos todos a un mismo archivo `subdominios_total.txt`.
>
>Como en ambos archivos existían dominios repetidos, los he limpiado de la siguiente manera:
>```bash
># Copiamos todos los subdominios a un archivo intermedio temporal
>cat subdominios_crt.txt > ./tmp.txt
>cat subdominios_subfinder.txt >> ./tmp.txt
>
># Ahora, este archivo contiene 471 subdominios, pero muchos de ellos estan repetidos
>wc -l tmp.txt
>471 tmp.txt
>
># Ahora ordenamos, eliminamos los subdominios repetidos y los movemos al archivo definitivo
>sort tmp.txt | uniq > subdominios_total.txt
>
>wc -l subdominios_total.txt
>298 subdominios_total.txt
>```

Una vez tenemos todos los subdominios, podemos ir iterando sobre el con un pequeño script que nos permita automatizar el reconocimiento de la infraestructura de dichos subdominios.

```bash
while read -r linea; do
    # Nos saltamos los subdominios con wildcards
    if [[ "$linea" == *"*"* ]; then
        continue
    fi

    # Tomamos la IP del subdominio
    IP=$(dig +short "$linea" | grep -oP '(?<!\d)(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}(?!\d)')

    # Si nos ha devuelto la IP del subdominio
    if [[ -n "$IP" ]; then
	    # Por cada IP devuelta, analizamos
        for sub_ip in $(echo "$IP"); do
            echo "WHOIS: $sub_ip ($linea)"
            whois "$sub_ip" | grep -iE "netname|orgname|country"
            echo "================================"
            echo ""
        done
    fi
done < subdominios_total.txt


# INTERESANTE
WHOIS: 108.128.225.61 (aws.duplex.snapchat.com)
NetName:        AMAZO-4
OrgName:        Amazon.com, Inc.
Country:        US
NetName:        AMAZON-DUB
OrgName:        Amazon Data Services Ireland Limited
Country:        IE
=======================

WHOIS: 128.245.136.249 (cloud.email.snapchat.com)
NetName:        SALESF-3
OrgName:        Salesforce, Inc.
Country:        US
=======================

WHOIS: 54.241.238.63 (focus.snapchat.com)     # <--- Interesante
NetName:        AMAZON-2011L
OrgName:        Amazon Technologies Inc.
Country:        US
=======================

WHOIS: 13.56.100.93 (focus.snapchat.com)
NetName:        AT-88-Z
OrgName:        Amazon Technologies Inc.
Country:        US
=======================

WHOIS: 216.198.54.11 (help.snapchat.com)
NetName:        ZENDESK-NETWORK
OrgName:        Zendesk, Inc.
Country:        US
=======================

WHOIS: 13.224.83.95 (image.email.snapchat.com)
NetName:        AT-88-Z
OrgName:        Amazon Technologies Inc.
Country:        US
NetName:        AMAZO-CF
OrgName:        Amazon.com, Inc.
Country:        US
=======================

WHOIS: 13.224.83.8 (image.email.snapchat.com)
NetName:        AT-88-Z
OrgName:        Amazon Technologies Inc.
Country:        US
NetName:        AMAZO-CF
OrgName:        Amazon.com, Inc.
Country:        US
=======================

WHOIS: 13.224.83.128 (image.email.snapchat.com)
NetName:        AT-88-Z
OrgName:        Amazon Technologies Inc.
Country:        US
NetName:        AMAZO-CF
OrgName:        Amazon.com, Inc.
Country:        US
=======================

WHOIS: 13.224.83.54 (image.email.snapchat.com)
NetName:        AT-88-Z
OrgName:        Amazon Technologies Inc.
Country:        US
NetName:        AMAZO-CF
OrgName:        Amazon.com, Inc.
Country:        US
=======================

<snip>
```

---
# Huella Tecnológica

>```bash
>https://sitereport.netcraft.com/?url=https://objetivo.es
>```

*Netcraft* no ofrece una API JSON gratuita con la que poder obtener los datos para un post-procesado automático, por lo que nos veremos obligados a usar la GUI de su aplicación web.

![Pasted image 20261031133123.png](./img/Pasted%20image%2020261031133123.png)

---
# Ficheros Expuestos

```bash
curl -s https://www.snapchat.com/robots.txt

# *
User-agent: *
Disallow: /verificationofemployment
Disallow: /static_files/deletion_request.pdf
Disallow: /static/gla/
Disallow: /invite/

# Meta-WebIndexer
User-agent: Meta-WebIndexer
Allow: /

# Meta-ExternalAgent
User-agent: Meta-ExternalAgent
Disallow: /

# Meta-ExternalFetcher
User-agent: Meta-ExternalFetcher
Disallow: /

# OAI-SearchBot
User-agent: OAI-SearchBot
Allow: /
Disallow: /getreplies
Disallow: /explore/

# ChatGPT-User
User-agent: ChatGPT-User
Allow: /
Disallow: /getreplies
Disallow: /explore/

# PerplexityBot
User-agent: PerplexityBot
Allow: /
Disallow: /getreplies
Disallow: /explore/

<snip>

# Host
Host: https://www.snapchat.com

# Sitemaps
Sitemap: https://www.snapchat.com/sitemap.xml
Sitemap: https://www.snapchat.com/lens/sitemap.xml
Sitemap: https://www.snapchat.com/sitemaps/place/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/profile/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/p/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/lens_creators/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/tag/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/topic/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/entertainment_funny/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/top_spotlights/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/local_city_leaf/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/local_nbhd_leaf/sitemap-index.xml
Sitemap: https://www.snapchat.com/sitemaps/local_city_hub/sitemap-index.xml
```

```bash
curl -s https://www.snapchat.com/.well-known/security.txt

Contact: https://hackerone.com/snapchat
Acknowledgements: https://hackerone.com/snapchat/hacktivity
Preferred-Languages: en
Canonical: https://snapchat.com/.well-known/security.txt
Policy: https://hackerone.com/snapchat
Hiring: https://careers.snap.com
```

---
# Histórico del sitio

>```bash
>curl -s 'https://web.archive.org/cdx/search/cdx?url=objetivo.es/*&collapse=urlkey&fl=original' | grep -iE '/api/|\.json'
># en el navegador: https://web.archive.org/web/*/objetivo.es*
>```

```bash
curl -s 'https://web.archive.org/cdx/search/cdx?url=snapchat.com/*&collapse=urlkey&fl=original' | grep -iE '/api/|\.json'

https://www.snapchat.com/.well-known/ai-plugin.json
https://www.snapchat.com/.well-known/assetlinks.json
https://www.snapchat.com/.well-known/gpc.json
```

---
# Servicios expuestos
## Shodan

![Pasted image 20261031130359.png](./img/Pasted%20image%2020261031130359.png)

```bash
# aws.duplex.snapchat.com
curl -s https://internetdb.shodan.io/108.128.225.61 | jq
{
  "cpes": [],
  "hostnames": [
    "ec2-108-128-225-61.eu-west-1.compute.amazonaws.com",
    "eu-west1-aws.duplex.sc-gw.com",
    "aws.duplex.snapchat.com"
  ],
  "ip": "108.128.225.61",
  "ports": [
    443
  ],
  "tags": [
    "cloud"
  ],
  "vulns": []
}

# image.email.snapchat.com
curl -s https://internetdb.shodan.io/13.224.83.54 | jq
{
  "cpes": [
    "cpe:/a:amazon:amazon_cloudfront"     # <---- Detras de un CDN
  ],
  "hostnames": [
    "server-13-224-83-54.mad53.r.cloudfront.net"    # <---- Detras de un CDN
  ],
  "ip": "13.224.83.54",
  "ports": [
    80,
    443
  ],
  "tags": [
    "cloud",
    "cdn"        # <---- Detras de un CDN
  ],
  "vulns": []
}

# focus.snapchat.com
curl -s https://internetdb.shodan.io/54.241.238.63 | jq
{
  "cpes": [
    "cpe:/a:amazon:elastic_load_balancing",   # <--- Balanceador de carga
    "cpe:/a:f5:nginx"
  ],
  "hostnames": [
    "workramp.io",   # <--- LMS (Learning Management System o Sistema de Gestión de Aprendizaje)
    "ec2-54-241-238-63.us-west-1.compute.amazonaws.com"
  ],
  "ip": "54.241.238.63",
  "ports": [
    80,
    443
  ],
  "tags": [
    "cloud",
    "pqc"
  ],
  "vulns": []
}
```

![Pasted image 20261031132032.png](./img/Pasted%20image%2020261031132032.png)

---
# Google Dorks

![Pasted image 20261031133437.png](./img/Pasted%20image%2020261031133437.png)

![Pasted image 20261031142700.png](./img/Pasted%20image%2020261031142700.png)

>Tras varias búsquedas, no encontramos nada interesante.

---
# Emails

Hasta ahora no hemos encontrado ningún correo electrónico de ningún empleado, por lo que no conocemos el formato de las direcciones de correo electrónico de la organización. No obstante, existen plataformas como ***[RocketReach](https://rocketreach.co/)*** en donde podemos encontrar información sobre la empresa.

![Pasted image 20261031223008.png](./img/Pasted%20image%2020261031223008.png)

Además, herramientas como ***[Hunter.io](https://hunter.io/)***, no pueden ayudar a encontrar correos electrónicos.

![Pasted image 20261031222618.png](./img/Pasted%20image%2020261031222618.png)

![Pasted image 20261101013304.png](./img/Pasted%20image%2020261101013304.png)

![Pasted image 20261101012626.png](./img/Pasted%20image%2020261101012626.png)

![Pasted image 20261101013605.png](./img/Pasted%20image%2020261101013605.png)
