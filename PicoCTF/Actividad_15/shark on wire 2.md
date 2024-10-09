## Objetivo 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
## Solución  
```bash
1104	991.587437	10.0.0.66	10.0.0.1	UDP	60	5000 → 22 Len=5
1106	993.672341	10.0.0.66	10.0.0.1	UDP	60	5112 → 22 Len=5
1118	1006.227400	10.0.0.66	10.0.0.1	UDP	60	5105 → 22 Len=5
1122	1008.323546	10.0.0.66	10.0.0.1	UDP	60	5099 → 22 Len=5
1124	1010.428768	10.0.0.66	10.0.0.1	UDP	60	5111 → 22 Len=5
1129	1012.535515	10.0.0.66	10.0.0.1	UDP	60	5067 → 22 Len=5
1131	1014.627130	10.0.0.66	10.0.0.1	UDP	60	5084 → 22 Len=5
1133	1016.719657	10.0.0.66	10.0.0.1	UDP	60	5070 → 22 Len=5
1135	1018.807279	10.0.0.66	10.0.0.1	UDP	60	5123 → 22 Len=5
1137	1020.899193	10.0.0.66	10.0.0.1	UDP	60	5112 → 22 Len=5
1139	1022.991480	10.0.0.66	10.0.0.1	UDP	60	5049 → 22 Len=5
1141	1025.083748	10.0.0.66	10.0.0.1	UDP	60	5076 → 22 Len=5
1143	1027.167730	10.0.0.66	10.0.0.1	UDP	60	5076 → 22 Len=5
1145	1029.255106	10.0.0.66	10.0.0.1	UDP	60	5102 → 22 Len=5
1147	1031.334799	10.0.0.66	10.0.0.1	UDP	60	5051 → 22 Len=5
1162	1043.850969	10.0.0.66	10.0.0.1	UDP	60	5114 → 22 Len=5
1164	1045.934960	10.0.0.66	10.0.0.1	UDP	60	5051 → 22 Len=5
1166	1048.019181	10.0.0.66	10.0.0.1	UDP	60	5100 → 22 Len=5
1172	1054.255069	10.0.0.66	10.0.0.1	UDP	60	5095 → 22 Len=5
1178	1060.507360	10.0.0.66	10.0.0.1	UDP	60	5100 → 22 Len=5
1180	1062.619741	10.0.0.66	10.0.0.1	UDP	60	5097 → 22 Len=5
1187	1066.779955	10.0.0.66	10.0.0.1	UDP	60	5116 → 22 Len=5
1189	1068.867478	10.0.0.66	10.0.0.1	UDP	60	5097 → 22 Len=5
1192	1070.959143	10.0.0.66	10.0.0.1	UDP	60	5095 → 22 Len=5
1196	1073.043525	10.0.0.66	10.0.0.1	UDP	60	5118 → 22 Len=5
1199	1075.127069	10.0.0.66	10.0.0.1	UDP	60	5049 → 22 Len=5
1267	1139.786992	10.0.0.66	10.0.0.1	UDP	60	5097 → 22 Len=5
1272	1141.870974	10.0.0.66	10.0.0.1	UDP	60	5095 → 22 Len=5
1274	1143.955404	10.0.0.66	10.0.0.1	UDP	60	5115 → 22 Len=5
1276	1146.043247	10.0.0.66	10.0.0.1	UDP	60	5116 → 22 Len=5
1284	1154.383039	10.0.0.66	10.0.0.1	UDP	60	5051 → 22 Len=5
1286	1156.475039	10.0.0.66	10.0.0.1	UDP	60	5103 → 22 Len=5
1296	1166.882937	10.0.0.66	10.0.0.1	UDP	60	5048 → 22 Len=5
1301	1168.975486	10.0.0.66	10.0.0.1	UDP	60	5125 → 22 Len=5
```
## Notas Adicionales 
Observamos que muchas peticiones se estaban direccionando hacia el mismo puerto y la misma direccion ip usando wireshark, entonces las filtramos para ver cada una, dentro de ellas la mayoria tenia texto sin sentido o que no nos hacia sentido, entonces no era buscar ahi, sino que en la columna donde todos los numero emepzaban con 5000 se podia ver un patron.
`1104	991.587437	10.0.0.66	10.0.0.1	UDP	60	5000 → 22 Len=5`

Asi que tomamos cada numero (sin incluir el primer 5) y vimos que eran codigos ascii que posteriormente pasamos a caracteres para obtener la flag.
```
000
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125
```
FLAG:
`picoCTF{p1LLf3r3d_data_v1a_st3g0}`
### Referencias
wireshark:
[Wireshark · Go Deep](https://www.wireshark.org/)