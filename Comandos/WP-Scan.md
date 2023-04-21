La herramienta WPScan es de gran utilidad para averiguar rápidamente posibles vulnaviridades (php, themes, users, plugins…) en «nuestros» wordpress.

A continuación los principales opciones del parámetro enumerate:

## 1. Buscar todos los plugins:

wpscan --url http://tudominio.com --enumerate p

## 2. Buscar plugins vulnerables:

wpscan --url http://tudominio.com --enumerate vp

## 3. Buscar themes:

wpscan --url http://tudominio.com --enumerate t

## 4. Buscar themes vulnerables:

wpscan --url http://tudominio.com --enumerate vt

## 5. Buscar usuarios:

wpscan --url http://tudominio.com --enumerate u

## 5. Buscar archivos timthumb:

wpscan --url http://tudominio.com --enumerate tt
