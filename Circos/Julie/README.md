### Utiiliser Circos

## Formater les données pour circos

On part du fichier .bedgraph de julie avec ce format :
Chr chr_start chr_end value

D'abord, je garde que les valeurs positives :
```
cat 'Galaxy62-[Kdm3_WT].bedgraph' | awk '$4>0 {print $0}' > roger_kdm3_pos_value.txt
```

On formate les données (le karyotype que j'ai chargé sur circos prend des Chr_name sous cette forme : "2L") :
```
sed -i 's/chr2L/2L/g' roger_kdm3_pos_value.txt 
```

Je sed de cette manière pour tout les chromosomes : 2L, 2R, 3R, 3L, 4 ,X et enfin Y.

## Les fichiers importants à modifier

Il faut ajouter le fichier Karyotype fourni dans ~/circos/current/data/karyotypes
Il faut ajouter le dossier Julie au complet dans ~/circos/current/

## Run la création du graph

Pour run la création du graph, il faut juste executer le script bash : run.exe
