## Objetivo
Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:60122/), and find the flag!
## Solución
```bash
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓ¡ÒÅ¤í";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    
```
## Notas Adicionales
En el textarea habia un codigo de javascript asi que lo que se tiene que hacer es simplemente copiar el texto y abrir la integracion de inspeccionar, irnos al apartado de consola, pegarlo y dar enter, asi obtenemos esta flag:
`picoCTF{p@g3_turn3r_0148cb05}`
### Referencias