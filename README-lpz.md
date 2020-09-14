Helpers pour trouver un terrain
### DVF
* Base « Demande de valeurs foncières » (avec descriptif des données): https://cadastre.data.gouv.fr/dvf
* App: https://app.dvf.etalab.gouv.fr

* Parcelles data url: `https://cadastre.data.gouv.fr/bundler/cadastre-etalab/communes/{40213}/geojson/parcelles`
** or : https://cadastre.data.gouv.fr/datasets/cadastre-etalab
* Parcelles data format:
```
[
  {
    "type": "Feature",
    "id": "402130000B0684",
    "geometry":{
      "type":"Polygon",
      "coordinates":[[[-1.3522938,43.6143632], ...]]
    },
    "properties": {
      "id": "402130000B0684",
      "commune": "40213",
      "prefixe": "000",
      "section": "B",
      "numero": "684",
      "contenance": 950,
      "arpente": true,
      "created": "2017-04-04",
      "updated": "2018-11-13"
    }
  },
  ...
]
```
* Mutations data url: https://app.dvf.etalab.gouv.fr/api/mutations3/{40213}/{0000A} or {http://localhost:3001}/api/mutations3/40213/0000A
** For comune 40213, section A coded `0000A`.
* Mutations data format (less relevant ones are shifted right):
```
{"mutations":
  [
    {
      "id_mutation":"2019-399629",
      "date_mutation":"2019-01-04",
      "numero_disposition":"1",
      "nature_mutation":"Vente",
      "valeur_fonciere":"313300.0",
        "adresse_numero":"nan",
        "adresse_suffixe":"None",
      "adresse_nom_voie":"MARAIS NORD",
      "adresse_code_voie":"B019",
      "code_postal":"40230",
      "code_commune":"40213",
      "nom_commune":"Orx",
      "code_departement":"40",
        "ancien_code_commune":"None",
        "ancien_nom_commune":"None",
      "id_parcelle":"402130000A0223",
      "ancien_id_parcelle":"None",
        "numero_volume":"None",
        "lot1_numero":"None",
        "lot1_surface_carrez":"None",
        "lot2_numero":"None",
        "lot2_surface_carrez":"None",
        "lot3_numero":"None",
        "lot3_surface_carrez":"None",
        "lot4_numero":"None",
        "lot4_surface_carrez":"None",
        "lot5_numero":"None",
        "lot5_surface_carrez":"None",
        "nombre_lots":"0",
        "code_type_local":"None",
        "type_local":"None",
        "surface_reelle_bati":"nan",
        "nombre_pieces_principales":"nan",
      "code_nature_culture":"E",
      "nature_culture":"eaux",
        "code_nature_culture_speciale":"None",
        "nature_culture_speciale":"None",
      "surface_terrain":"843.0",
      "longitude":"-1.351913",
      "latitude":"43.618359",
      "section_prefixe":"0000A"
    },
    ...
  ]
}
```
See below #Land classification.




* Mutations data url: https://app.dvf.etalab.gouv.fr/api/mutations/<commune>/from=<dateminimum>&to=<datemaximum>




### Cadastre :
* URL: https://www.cadastre.gouv.fr/scpc/rechercherParReferenceCadastrale.do#
* Open "URL" > Login > Tab "Rechercher"
* "Préférer une recherche par références cadastrales": click > "Ma recherche": click > "Par parcelle": click > Fill the fields
* DATA (Geojson): https://cadastre.data.gouv.fr/datasets/cadastre-etalab

### Google maps
Use the coordinates from the parcelle data to link to the google maps view :
* URL: https://www.google.com/maps/@{lat},{lon},137m/data=!3m1!1e3


### Land classification
Mutations are accompanied with nature of the land, via both code and full French language. [Source]()
```
Code Nature de Culture	Libellé Nature de Culture
AB	terrains a bâtir
AG	terrains d'agrément
B	bois
BF	futaies feuillues
BM	futaies mixtes
BO	oseraies
BP	peupleraies
BR	futaies résineuses
BS	taillis sous futaie
BT	taillis simples
CA	carrières
CH	chemin de fer
E	eaux
J	jardins
L	landes
LB	landes boisées
P	prés
PA	pâtures
PC	pacages
PE	prés d'embouche
PH	herbages
PP	prés plantes
S	sols
T	terres
TP	terres plantées
VE	vergers
VI	vignes
```
