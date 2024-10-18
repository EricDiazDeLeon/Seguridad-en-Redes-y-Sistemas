## Objetivo 
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act18$ nc jupiter.challenges.picoctf.org 39894  
-------------------------------------------------------------------------------  
kvaqxocg zhxh dg tvix yjoq - yxhlihakt_dg_k_vmhx_jofwpo_oqyjkqctih  
-------------------------------------------------------------------------------  
sh shxh avc fikz fvxh czoa o lioxchx vy oa zvix vic vy vix gzdn cdjj sh gos zhx gdau, oap czha d iaphxgcvvp yvx czh ydxgc cdfh szo  
c sog fhoac wt o gzdn yviaphxdaq da czh gho.  d figc okuavsjhpqh d zop zoxpjt hthg cv jvvu in szha czh ghofha cvjp fh gzh sog gdau  
daq; yvx yxvf czh fvfhac czoc czht xoczhx nic fh dacv czh wvoc czoa czoc d fdqzc wh godp cv qv da, ft zhoxc sog, og dc shxh, phop  
sdczda fh, noxcjt sdcz yxdqzc, noxcjt sdcz zvxxvx vy fdap, oap czh czviqzcg vy szoc sog thc whyvxh fh.  
kali@KaliEND:~/Downloads/PicoCTF/Act18$
```
## Notas Adicionales 
usamos una herramienta de deteccion de cipher, y descubrimos que es un cipher de tipo substitution, para lo cual utilice otra herramienta especializada en decifrar ciper substitution y obtube el siguiente texto:
```
------------------------------------------------------------------------------- CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_AGFLCGTYUE ------------------------------------------------------------------------------- WE WERE NOT MUCH MORE THAN A QUARTER OF AN HOUR OUT OF OUR SHIP TILL WE SAW HER SINK, AND THEN I UNDERSTOOD FOR THE FIRST TIME WHAT WAS MEANT BY A SHIP FOUNDERING IN THE SEA. I MUST ACKNOWLEDGE I HAD HARDLY EYES TO LOOK UP WHEN THE SEAMEN TOLD ME SHE WAS SINKING; FOR FROM THE MOMENT THAT THEY RATHER PUT ME INTO THE BOAT THAN THAT I MIGHT BE SAID TO GO IN, MY HEART WAS, AS IT WERE, DEAD WITHIN ME, PARTLY WITH FRIGHT, PARTLY WITH HORROR OF MIND, AND THE THOUGHTS OF WHAT WAS YET BEFORE ME.
```
en las pistas dentro de picoCTF especifica claramente que esta flag no tiene el formato normal, por lo que la flag es: 

`FREQUENCY_IS_C_OVER_LAMBDA_AGFLCGTYUE`
### Referencias
boxentriq cipher identifier
https://www.boxentriq.com/code-breaking/cipher-identifier

cipher substitution decoder:
https://planetcalc.com/8047/