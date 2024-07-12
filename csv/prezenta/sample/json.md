# Informatii generale

Pentru exemplificare se poate acesa site-ul de prezenta ale ultimelor alegeri locale:
```
https://prezenta.roaep.ro/locale27092020
```


## 1. Nomenclatoare
Nomenclatoare SIMPV (date despre voturi) ce pot fi descarcate 1 singura data:
```
https://prezenta.roaep.ro/locale27092020/data/json/simpv/lists/counties.json
https://prezenta.roaep.ro/locale27092020/data/json/simpv/lists/uats_ab.json
https://prezenta.roaep.ro/locale27092020/data/json/simpv/lists/localities_ab.json
https://prezenta.roaep.ro/locale27092020/data/json/simpv/lists/precincts_ab.json
```

Nomenclatoare SICPV (date despre procese verbale) ce pot fi descarcate 1 singura data:
```
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/lists/counties.json
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/lists/uats_ab.json
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/lists/localities_ab.json
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/lists/precincts_ab.json
```

Pentru fiecare judet exista cate un fisier `uats_XX.json`, `localities_XX.json`, `precincts_XX.json`


## 2. Voturi

Informatiile despre voturi se actualizeaza la fiecare minut:
```
https://prezenta.roaep.ro/locale27092020/data/json/simpv/presence/presence_ab_now.json
```

Suplimentar exista si date istorice din ora in ora:
```
https://prezenta.roaep.ro/locale27092020/data/json/simpv/presence/presence_ab_2020-09-27_21-00.json
```

Sunt impartite pe judet. Ex pentru Prahova se poate inlocui `_ab_` cu `_ph_`:
```
https://prezenta.roaep.ro/locale27092020/data/json/simpv/presence/presence_ph_2020-09-27_21-00.json
```


## 3. Procese verbale

Informatiile despre procese verbale se genereaza la 5 minute.
Sunt impartite per judet si fiecare judet are cele 3 categorii: provizorii, partiale si finale.

```
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/pv/pv_ab_prov.json
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/pv/pv_ab_part.json
https://prezenta.roaep.ro/locale27092020/data/json/sicpv/pv/pv_ab_final.json
```

JSON-ul contine urmatoarea structura:
```
1. stages.${stageCode}.scopes.${scopeCode}.categories.${categoryCode}.files.${teritoryId}          -> fisiere PV-uri
2. stages.${stageCode}.scopes.${scopeCode}.categories.${categoryCode}.table.${teritoryId}.fields`  -> campuri din PV-uri (a, a1, a2, a3, a4, b, b1, b2, b3, b4, c, d, e,f )
3. stages.${stageCode}.scopes.${scopeCode}.categories.${categoryCode}.table.${teritoryId}.votes`   -> voturi candidati din PV-uri
```

Valori posibile pentrun campurile cod:

1. stageCode
```
- PROV
- PART
- FINAL
```

2.scopeCode
```
- PRCNCT
- UAT
- CNTY
- CNTRY
```

3.categoryCode
```
- P
- CL
- CJ
- PCJ
```

4. teritoryId
```
if  (scopeCode = PRCNCT) -> precinct_id
if  (scopeCode = UAT)    -> uat_id
if  (scopeCode = CNTY)   -> county_id 
if  (scopeCode = CNTRY)  -> RO 
```



## Diferente pentru Europarlamentare:
- Regulile pentru `1. Nomenclatoare` si `2. Voturi` raman valabile.
- Suplimentar, pe langa codurile de judet obisnuite, exista un cod nou "sr" pentru "Strainatate" si in fisierul `/data/json/simpv/lists/uats_sr.json` vom avea lista de tari.
- La `3. Procese verbale` vom avea un singur `categoryCode = EUP` 
- La calea `stages.${stageCode}.scopes.${scopeCode}.categories.${categoryCode}.table.${teritoryId}.fields` exista alte campuri: a, a1, a2, b, b1, b2, b3, c, d, e, f



## URL-urile viitoarelor alegeri:
```
https://prezenta.roaep.ro/locale09062024
https://prezenta.roaep.ro/europarlamentare09062024
```

