
## Técnicas de information gathering
Gathering-OSINT = Recabar info de fuentes abiertas

### Whois
A quién pertenece un dominio.

```shell
whois marca.com
```
### Ripe

A quien pertenecen ips públicas.
https://apps.db.ripe.net/db-web-ui/query

Ejemplo ayuntamiento:
https://apps.db.ripe.net/db-web-ui/query?bflag=false&dflag=false&rflag=true&searchtext=ayuntamiento&source=RIPE


```bash
whois -h whois.ripe.net -- '--resource <objetivo>'
whois -h whois.ripe.net -- '--resource ayuntamiento'
```

### Dnsdumpster

https://dnsdumpster.com/

### crt.sh
Encontrar subdominios.
https://crt.sh/

Ejemplo https://crt.sh/?q=mediamarkt.es

### Censys 
https://search.censys.io/

Escaneo sin realizar ninguna acción, no deja rastro.

Ejemplo: https://search.censys.io/hosts/194.233.193.25

### Host
Para sabe la ip a través del nombre de dominio
```shell
host colegiosons.es
```

### NSLOOKUP - Windows
```
nslookup
```

### Dig
``
```shell
 dig ANY viu.es 
```

#### Transferencia de zona
```shell
dig axfr @ns1.dominio.net dominio.net
```

Ejemplo práctico entorno lab:
```shell
dig axfr @nsztm1.digi.ninja zonetransfer.me
```


### Google Hacking | Dorking 

Ejemplo de búsqueda: 
	• inurl:/intranet/login.php 
	• inurl:”CgiStart?page=” 
	• intitle:"Index of" "/wp-content/uploads" 
	• intitle:"Index of" "DCIM“

https://www.exploit-db.com/google-hacking-database

### Robots.txt
Un archivo **robots.txt** indica a los rastreadores de los buscadores a qué URLs del sitio web sitio pueden acceder. El archivo robots.txt se encuentra en la raíz del directorio web. En muchas ocasiones, este archivo proporciona información sobre rutas y directorios de la aplicación web.
https://www.mediamarkt.es/robots.txt

### Pastebin
Bloc de notas público.
Se usa frecuentemente para publicar leaks de información derivados del compromiso de empresas
https://pastebin.com/
Pastebin no es la única aplicación de este estilo, podemos encontrar gran número de aplicaciones similares: 
	• cl1p 
	• codepad 
	• controlc 
	• doxbin 
	• dpaste 
	• dpaste2
	• dumpz 
	• 0bin 
	• Obin 
	• paste.debian 
	• paste.ee 
	• paste.centos
### Tinfoleak
obtener información de empleados, emails, eventos, tecnologías, etc. de una forma simple y generalmente anónima.
https://tinfoleak.com/
Otras recursos interesantes: 
[https ://github.com/jivoi/awesome-osint](https ://github.com/jivoi/awesome-osint)
[Cámaras en el mundo](https ://calculator.ipvm.com)

## Escaneos de red y enumeración

Un escáner de red es una herramienta que identifica hosts activos con sus direcciones IP correspondientes. Una vez enumerados todos los hosts, se envían paquetes a puertos específicos y se analizan las respuestas para reconocer los servicios en ejecución. Este proceso es mucho más intrusivo que las técnicas en fuentes abiertas

### Nmap

```shell
nmap <parámetros> <hosts>
```
Parámetros: 
* -p: puertos a escanear, por ejemplo 1-1024. Por defecto escanea los más comunes. 
* -s: 
* -sT: TCP Scan 
* -sS: SYN Scan 
* -sU: UDP Scan 
Otras 
* -v: verbose. 
* -sn: no realizar escaneo de puertos. 
* -Pn: omitir ping y escanear siempre. 
* -T: del 0 al 5 realizará el escaneo más rápido/lento. 
* -oN : Guardará el resultado en un archivo. 
* -oG : guardará el resultado en un archivo (grep friendly).