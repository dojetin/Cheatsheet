# NMAP

NMAP es una de las mejores herramientas de enumeración de objetivos. En función de cómo la utilicemos, nuestras pruebas serán más o menos sigilosas.

## Comandos

Nmap dispone de un modo automático, que sólo necesita que se le pase por parámetro la IP o Dominio a escanear. Se le pueden especificar varias IPs o Dominios, incluso, IPs consecutivas, separando por coma la trama final que varía. 

```
nmap 1.1.1.1.
nmap google.com 8.8.8.8
nmap 1.1.1.1,2,3,4
```

También le podemos especificar que escanee un puerto concreto, o un rango de puertos.

```
nmap -p 1-65535  1.1.1.1
nmap -p 80,443 8.8.8.8
```

Es posible, escanear sólo los puertos más populares, así hacemos que sea mucho más rápido

```
nmap --top-ports 20 192.168.1.10
```

En caso de necesitar que el escaneo sea de toda la red, bastaría con proporcionar su máscara

```
nmap 192.168.1.0/24
```

Si necesitamos (es recomendable) guardar el reporte del escaneo, bastaría con utilizar la sintaxis -oN nombrefichero.xml

```
nmap -oN output.txt securitytrails.com
```

En muchas ocasiones, la resolución DNS puede afectar a los resultados, por lo que solemos utilizar el parámetro -n

```
nmap -p 80 -n 8.8.8.8
```

Identificar Sistema Operativo de la víctima
```
nmap -O 192.168.0.164
```

Identificar Servicios y versiones de la víctima
```
nmap -sV 192.168.0.164
```

Identificar Firewall
```
nmap -sA 192.168.0.101
```

Evadir Firewall
```
nmap -Pn 192.168.0.101
```

Nmap dispone de varios comandos automáticos de escaneo avanzados, este es bastante agresivo (ruidoso)

```
nmap -A -T4 cloudflare.com
```

Modo cauteloso (silencioso

```
nmap -sS 192.168.0.101
```


## Scripts

Si ya la herramienta Nmap es avanzada, se puede enriquecer con el uso de scripts.

```
nmap -sS -sV -O -v 86.109.122.114 -n --min-rate 4000 --script vuln -oA CLIENTES/coas/map86

```
