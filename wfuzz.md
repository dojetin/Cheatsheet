# WFUZZ

## Carpetas
wfuzz -c --hc=404 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt beehackers.es/FUZZ

## Subdominios
wfuzz -c -f sub-fighter -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u 'http://schooled.htb' -H "Host: FUZZ.schooled.htb" --hw 290
