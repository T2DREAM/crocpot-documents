**Convert BED file to TABIX**

The BED file are generated using various Long Range Chromatin interaction pipelines described in our [methods section](http://www.apps.t2depigenome.org/locuszoom-dev/methods.html)

```
Example BED file

chr1    762519  763197  1:1051216-1052110_C1orf159      0.0604648523272884
chr1    762519  763197  1:1208894-1209818_UBE2J2        0.0932539156350098
chr1    762519  763197  1:1310295-1311106_AURKAIP1      0.150361770291683
chr1    762519  763197  1:1342116-1343257_MRPL20        0.15508410270037
chr1    762519  763197  1:1354928-1355902_ANKRD65       0.0643913981277296
chr1    762519  763197  1:1356146-1356933_ANKRD65       0.161359288419506
```

Tabix files are indexed position sorted files in TAB-delimited formats. TABIX files enable genome viewers to support huge data files and remote custom tracks over networks.

Reference: [Tabix: fast retrieval of sequence features from generic TAB-delimited files](https://academic.oup.com/bioinformatics/article/27/5/718/262743)

**Create TABIX files**

```
//Sort the BED file

bedtools sort -i beta.bed > beta_sorted.bed

//Compress the file and run tabix

bgzip beta_sorted.bed

tabix -p bed beta_sorted.bed.gz
```

