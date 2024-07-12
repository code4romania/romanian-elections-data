## Informatii generale
Vom avea 2 FTP-uri. Unul pentru date legate prezenta si unul pentru date din procesel verbale.

In fiecare va exista cate 1 folder pentru fiecare proces electoral (ex. LCL-20240609)

```
https://prezenta.roaep.ro/presa/prezenta
https://prezenta.roaep.ro/presa/pv
```

## Nume fisiere:

- Pt prezenta:
    - `presence_2024-06-09_12-10.csv` (generate si persistate la intervale de 10 min)

- Pt procese verbale: (generate si suprasrise la intervale de 5 min)
  - `pv_<stage_code>_<scope_code>_<report_type_category>_<teritorial_identification>.csv`

#### Exemple:
```
  pv_prov_uat_p_<county_code 2 letters>_<siruta>.csv (Fiecare rand contine informatii despre o sectie de votare din UAT, pentru PV primar )
  pv_prov_cnty_p_<county_code 2 letters>.csv (Fiecare rand contine informatii despre un UAT din judet, pentru PV primar)
  pv_prov_cntry_p.csv
```



## Valori posibile pentrun campurile cod:

1. stage_code:
```
- PROV
- PART
- FINAL
```

2.scope_code:
```
- PRCNCT
- UAT
- CNTY
- CNTRY
```

3.report_type_category:
```
- P
- CL
- CJ
- PCJ

- EUP (Pentru europarlamentare)
```


4.report_type_code:
```
- P_SV
- P_CE
- P_BEJ
- P_SV_SECTOR
- P_CE_SECTOR
- P_BEMB
- P_BEC
- CL_SV
- CL_CE
- CL_BEJ
- CL_SV_SECTOR
- CL_CE_SECTOR
- CL_BEMB
- CL_BEC
- CJ_SV
- CJ_BEJ
- CGMB_SV
- CGMB_CEMB
- CJ_BEC
- CGMB_BEC
- PCJ_SV
- PCJ_BEJ
- PG_SV
- PG_CEMB
- PCJ_BEC
- PG_BEC

- EUP_SV
- EUP_SV_SECTOR
- EUP_SV_SR (strainatate)
- EUP_BEJ
- EUP_BESMB
- EUP_BESVS
```