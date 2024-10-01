# Companies

## Get All Companies

> The above command returns JSON structured like this:

```json
[
  {
    "id": 72242,
    "siren": 831946488,
    "siret": 83194648800010,
    "siege": true,
    "social_name": "OPEN TOURISME LAB NIMES METROPOLE",
    "sirets": [
      {
        "siret": 83194648800123,
        "type": 75008
      },
      {
        "siret": 83194648800128,
        "type": 75019
      }
    ],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/2438"
      },
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/24384"
      }
    ]
  }
]
```

This endpoint retrieves all companies.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/companies`

### Query Parameters

| Field      | Type                  | Description                                                                                       |
|------------|-----------------------|---------------------------------------------------------------------------------------------------|
| siren      | Entier                | Unique ID de l'entreprise                                                                          |
| term       | Chaîne de caractères   | Terme de recherche                                                                                |
| limit      | Entier                | Nombre maximum d'entreprises retournées                                                            |
| offset     | Entier                | Nombre de départ pour les entreprises retournées (utile pour paginer les résultats)              |
| order      | Chaîne de caractères   | Champ de commande pour les résultats                                                              |
| updatedAt  | Chaîne de caractères   | Direction de tri                                                                                   |
| sort       | Chaîne de caractères   | Direction de tri                                                                                   |
| meta       | Booléen               | Informations de pagination à la sortie                                                              |
| _format    | Chaîne de caractères   | Format de sortie                                                                                   |


### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

| Field           | Type                  | Description                                                                                  |
|------------------|-----------------------|----------------------------------------------------------------------------------------------|
| id               | Entier                | Identifiant unique de l'entreprise                                                            |
| siren            | Entier                | Numéro SIREN de l'entreprise                                                                  |
| siret            | Entier                | Numéro SIRET de l'entreprise                                                                  |
| siege            | Booléen               | Indique si l'entreprise est un siège social (true/false)                                    |
| social_name      | Chaîne de caractères   | Nom social de l'entreprise                                                                    |
| sirets           | Tableau[]             | Liste des SIRET de l'entreprise avec leurs types                                             |
| sirets.siret     | Entier                | Numéro SIRET associé à l'entreprise                                                           |
| sirets.type      | Entier                | Type associé au SIRET                                                                          |
| links            | Tableau[]             | Liste des liens associés à l'entreprise                                                       |
| links.rel        | Chaîne de caractères   | Relation du lien                                                                                |
| links.href       | Chaîne de caractères   | URL du lien                                                                                   |

[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## Find Company by ID

> The above command returns JSON structured like this:

```json
[
  {
    "id": 72242,
    "siren": 831946488,
    "siret": 83194648800010,
    "siege": true,
    "social_name": "OPEN TOURISME LAB NIMES METROPOLE",
    "sirets": [
      {
        "siret": 83194648800123,
        "type": 75008
      },
      {
        "siret": 83194648800128,
        "type": 75019
      }
    ],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/2438"
      },
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/24384"
      }
    ],
    "last_modified": "2015-08-28 03:40:48",
    "enseigne": "Burger King",
    "sigle": "LCL",
    "rcs": "RCS Paris 654 987 321",
    "tva_number": "FR76662042449",
    "index_euro": 998209,
    "immatriculation_date": "01/07/1966",
    "naf_code": "6419Z - Autres intermédiations monétaires",
    "juridic_form": "Autre SA à conseil d'administration",
    "type_etablissement": "1",
    "categorie_full": "Autres intermédiations monétaires",
    "category_light": "banque et assurance",
    "capital_social": 2499597122,
    "fonds_propres": 344069905,
    "ca_bilan": 44069905,
    "effectif_precis": 43200,
    "resultat_net": 3645976,
    "resultat_exploitation": 645976,
    "radiate": false,
    "indice_risque_info_legal": "Risque faible",
    "indice_risque_score3": 5,
    "anne_indice_risque_score3": 2017,
    "nb_filliales_directes\"": 2,
    "nb_filliales_indirectes\"": 2,
    "address": "1762 route de Pontenx",
    "zip": "40160",
    "city": "PARENTIS-EN-BORN",
    "department": "Landes",
    "country": "France",
    "geo_lat": 44.342170715332,
    "geo_long": -1.0811624526978,
    "telephone_number": "05 58 82 95 00",
    "fax_number": "01 42 82 12 99",
    "web_site": "//google.fr",
    "url_maps\"": "44.3351073;-1.0852105000000165",
    "url_viadeo\"": "",
    "url_twitter\"": "",
    "url_gnews\"": "",
    "url_wikipedia\"": "",
    "url_facebook\"": "",
    "url_linkedin\"": "",
    "url_score3\"": "//www.score3.fr/VERMILION-REP-SAS-410964837.shtml",
    "url_scoopit\"": "",
    "logo_url\"": "",
    "email_contact\"": "contact@mycompany.com",
    "contacts": [
      {
        "name": "mr X",
        "role": "Président"
      },
      {
        "name": "Miss Y",
        "role": "Directeur général"
      }
    ],
    "nb_actes": 5
  }
]
```

This endpoint retrieves some company by its ID.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/companies/{companyId}`

### Query Parameters

Field         | Type                | Description                                     
--------------|---------------------|-------------------------------------------------
companyId *   | Entier     | ID of the company to return (ex: 2105)            
_format       | Chaine de caractères | Output format (Default value: json)              


### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

Field                          | Type                      | Description                                            
-------------------------------|---------------------------|---------------------------------------------------------
id                              | entier                    | Identifiant unique de l'entreprise                                 
siren                           | entier                    | Numéro SIREN (identifiant unique à 9 chiffres)                 
siret                           | entier                    | Numéro SIRET (identifiant de l’établissement à 14 chiffres)         
siege                           | booléen                   | Indique si c'est le siège social                      
social_name                     | chaîne de caractères      | Raison sociale de l'entreprise                               
sirets                          | tableau                   | Liste des numéros SIRET associés                           
sirets.siret                    | entier                    | Numéro SIRET de l'établissement                       
sirets.type                     | entier                    | Code de type de l'établissement                          
links                           | tableau                   | Liste des liens associés                                    
links.rel                       | chaîne de caractères      | Type de relation                                           
links.href                      | chaîne de caractères      | URL vers les informations de l'entreprise                              
last_modified                   | chaîne de caractères (date-heure) | Date de dernière modification des informations de l'entreprise       
enseigne                        | chaîne de caractères      | Nom commercial de l'entreprise                               
sigle                           | chaîne de caractères      | Sigle de l'entreprise                         
rcs                             | chaîne de caractères      | Numéro d’immatriculation au registre du commerce et des sociétés (RCS)      
tva_number                      | chaîne de caractères      | Numéro de TVA                                              
index_euro                      | entier                    | Indice européen pour les informations de l'entreprise                  
immatriculation_date             | chaîne de caractères (date) | Date d’immatriculation                                    
naf_code                        | chaîne de caractères      | Code NAF et description de l'activité                       
juridic_form                    | chaîne de caractères      | Forme juridique de l'entreprise                               
type_etablissement              | chaîne de caractères      | Type d'établissement                                   
categorie_full                  | chaîne de caractères      | Description complète de la catégorie                               
category_light                  | chaîne de caractères      | Description légère de la catégorie                              
capital_social                  | entier                    | Capital social de l'entreprise                            
fonds_propres                   | entier                    | Fonds propres                                          
ca_bilan                        | entier                    | Chiffre d’affaires selon le bilan                         
effectif_precis                 | entier                    | Nombre précis d’employés                             
resultat_net                    | entier                    | Résultat net                                              
resultat_exploitation           | entier                    | Résultat d'exploitation                                        
radiate                         | booléen                   | Indique si l'entreprise est radiée             
indice_risque_info_legal        | chaîne de caractères      | Indice de risque légal                                        
indice_risque_score3            | entier                    | Score de risque selon Score3                          
anne_indice_risque_score3       | entier                    | Année du score de risque Score3                           
nb_filliales_directes           | entier                    | Nombre de filiales directes                           
nb_filliales_indirectes         | entier                    | Nombre de filiales indirectes                         
address                         | chaîne de caractères      | Adresse complète                                          
zip                             | chaîne de caractères      | Code postal                                             
city                            | chaîne de caractères      | Ville                                                    
department                      | chaîne de caractères      | Département                                              
country                         | chaîne de caractères      | Pays                                                 
geo_lat                         | nombre à virgule flottante| Latitude géographique                                   
geo_long                        | nombre à virgule flottante| Longitude géographique                                  
telephone_number                | chaîne de caractères      | Numéro de téléphone                                        
fax_number                      | chaîne de caractères      | Numéro de fax                                              
web_site                        | chaîne de caractères      | URL du site web                                             
url_maps                        | chaîne de caractères      | URL de la localisation sur Google Maps                                        
url_viadeo                      | chaîne de caractères      | URL du profil Viadeo (si disponible)                       
url_twitter                     | chaîne de caractères      | URL du profil Twitter (si disponible)                      
url_gnews                       | chaîne de caractères      | URL vers Google News (si disponible)                          
url_wikipedia                   | chaîne de caractères      | URL de la page Wikipédia (si disponible)                       
url_facebook                    | chaîne de caractères      | URL du profil Facebook (si disponible)                     
url_linkedin                    | chaîne de caractères      | URL du profil LinkedIn (si disponible)                     
url_score3                      | chaîne de caractères      | URL du profil Score3                                      
url_scoopit                     | chaîne de caractères      | URL du profil Scoop.it (si disponible)                     
logo_url                        | chaîne de caractères      | URL du logo de l'entreprise                               
email_contact                   | chaîne de caractères      | Adresse e-mail de contact                                   
contacts                        | tableau                   | Liste des contacts de l'entreprise                                
contacts.name                   | chaîne de caractères      | Nom de la personne de contact                              
contacts.role                   | chaîne de caractères      | Rôle ou fonction du contact                         
nb_actes                        | entier                    | Nombre d'actes liés à l'entreprise

[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## Find list of companies by IDs

> The above command returns JSON structured like this:

```json
[
  {
    "id": 72242,
    "siren": 831946488,
    "siret": 83194648800010,
    "siege": true,
    "social_name": "OPEN TOURISME LAB NIMES METROPOLE",
    "sirets": [
      {
        "siret": 83194648800123,
        "type": 75008
      },
      {
        "siret": 83194648800128,
        "type": 75019
      }
    ],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/2438"
      },
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/24384"
      }
    ],
    "last_modified": "2015-08-28 03:40:48",
    "enseigne": "Burger King",
    "sigle": "LCL",
    "rcs": "RCS Paris 654 987 321",
    "tva_number": "FR76662042449",
    "index_euro": 998209,
    "immatriculation_date": "01/07/1966",
    "naf_code": "6419Z - Autres intermédiations monétaires",
    "juridic_form": "Autre SA à conseil d'administration",
    "type_etablissement": "1",
    "categorie_full": "Autres intermédiations monétaires",
    "category_light": "banque et assurance",
    "capital_social": 2499597122,
    "fonds_propres": 344069905,
    "ca_bilan": 44069905,
    "effectif_precis": 43200,
    "resultat_net": 3645976,
    "resultat_exploitation": 645976,
    "radiate": false,
    "indice_risque_info_legal": "Risque faible",
    "indice_risque_score3": 5,
    "anne_indice_risque_score3": 2017,
    "nb_filliales_directes\"": 2,
    "nb_filliales_indirectes\"": 2,
    "address": "1762 route de Pontenx",
    "zip": "40160",
    "city": "PARENTIS-EN-BORN",
    "department": "Landes",
    "country": "France",
    "geo_lat": 44.342170715332,
    "geo_long": -1.0811624526978,
    "telephone_number": "05 58 82 95 00",
    "fax_number": "01 42 82 12 99",
    "web_site": "//google.fr",
    "url_maps\"": "44.3351073;-1.0852105000000165",
    "url_viadeo\"": "",
    "url_twitter\"": "",
    "url_gnews\"": "",
    "url_wikipedia\"": "",
    "url_facebook\"": "",
    "url_linkedin\"": "",
    "url_score3\"": "//www.score3.fr/VERMILION-REP-SAS-410964837.shtml",
    "url_scoopit\"": "",
    "logo_url\"": "",
    "email_contact\"": "contact@mycompany.com",
    "contacts": [
      {
        "name": "mr X",
        "role": "Président"
      },
      {
        "name": "Miss Y",
        "role": "Directeur général"
      }
    ],
    "nb_actes": 5
  }
]
```

This endpoint retrieves some company by its ID.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/companies/collection`

### Query Parameters

Champ         | Type               | Description                                      
--------------|--------------------|--------------------------------------------------
listIds       | tableau de chaînes | Identifiants (IDs) des entreprises à retourner     
_format       | chaîne de caractères| Format de sortie                                  
|                    | Valeurs disponibles : json, xml                  
|                    | Valeur par défaut : json


### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

[//]: # (c'est une répétition par rapport au precedentes responses)

Field                          | Type                      | Description                                            
-------------------------------|---------------------------|---------------------------------------------------------
id                              | entier                    | Identifiant unique de l'entreprise                                 
siren                           | entier                    | Numéro SIREN (identifiant unique à 9 chiffres)                 
siret                           | entier                    | Numéro SIRET (identifiant de l’établissement à 14 chiffres)         
siege                           | booléen                   | Indique si c'est le siège social                      
social_name                     | chaîne de caractères      | Raison sociale de l'entreprise                               
sirets                          | tableau                   | Liste des numéros SIRET associés                           
sirets.siret                    | entier                    | Numéro SIRET de l'établissement                       
sirets.type                     | entier                    | Code de type de l'établissement                          
links                           | tableau                   | Liste des liens associés                                    
links.rel                       | chaîne de caractères      | Type de relation                                           
links.href                      | chaîne de caractères      | URL vers les informations de l'entreprise                              
last_modified                   | chaîne de caractères (date-heure) | Date de dernière modification des informations de l'entreprise       
enseigne                        | chaîne de caractères      | Nom commercial de l'entreprise                               
sigle                           | chaîne de caractères      | Sigle de l'entreprise                         
rcs                             | chaîne de caractères      | Numéro d’immatriculation au registre du commerce et des sociétés (RCS)      
tva_number                      | chaîne de caractères      | Numéro de TVA                                              
index_euro                      | entier                    | Indice européen pour les informations de l'entreprise                  
immatriculation_date             | chaîne de caractères (date) | Date d’immatriculation                                    
naf_code                        | chaîne de caractères      | Code NAF et description de l'activité                       
juridic_form                    | chaîne de caractères      | Forme juridique de l'entreprise                               
type_etablissement              | chaîne de caractères      | Type d'établissement                                   
categorie_full                  | chaîne de caractères      | Description complète de la catégorie                               
category_light                  | chaîne de caractères      | Description légère de la catégorie                              
capital_social                  | entier                    | Capital social de l'entreprise                            
fonds_propres                   | entier                    | Fonds propres                                          
ca_bilan                        | entier                    | Chiffre d’affaires selon le bilan                         
effectif_precis                 | entier                    | Nombre précis d’employés                             
resultat_net                    | entier                    | Résultat net                                              
resultat_exploitation           | entier                    | Résultat d'exploitation                                        
radiate                         | booléen                   | Indique si l'entreprise est radiée             
indice_risque_info_legal        | chaîne de caractères      | Indice de risque légal                                        
indice_risque_score3            | entier                    | Score de risque selon Score3                          
anne_indice_risque_score3       | entier                    | Année du score de risque Score3                           
nb_filliales_directes           | entier                    | Nombre de filiales directes                           
nb_filliales_indirectes         | entier                    | Nombre de filiales indirectes                         
address                         | chaîne de caractères      | Adresse complète                                          
zip                             | chaîne de caractères      | Code postal                                             
city                            | chaîne de caractères      | Ville                                                    
department                      | chaîne de caractères      | Département                                              
country                         | chaîne de caractères      | Pays                                                 
geo_lat                         | nombre à virgule flottante| Latitude géographique                                   
geo_long                        | nombre à virgule flottante| Longitude géographique                                  
telephone_number                | chaîne de caractères      | Numéro de téléphone                                        
fax_number                      | chaîne de caractères      | Numéro de fax                                              
web_site                        | chaîne de caractères      | URL du site web                                             
url_maps                        | chaîne de caractères      | URL de la localisation sur Google Maps                                        
url_viadeo                      | chaîne de caractères      | URL du profil Viadeo (si disponible)                       
url_twitter                     | chaîne de caractères      | URL du profil Twitter (si disponible)                      
url_gnews                       | chaîne de caractères      | URL vers Google News (si disponible)                          
url_wikipedia                   | chaîne de caractères      | URL de la page Wikipédia (si disponible)                       
url_facebook                    | chaîne de caractères      | URL du profil Facebook (si disponible)                     
url_linkedin                    | chaîne de caractères      | URL du profil LinkedIn (si disponible)                     
url_score3                      | chaîne de caractères      | URL du profil Score3                                      
url_scoopit                     | chaîne de caractères      | URL du profil Scoop.it (si disponible)                     
logo_url                        | chaîne de caractères      | URL du logo de l'entreprise                               
email_contact                   | chaîne de caractères      | Adresse e-mail de contact                                   
contacts                        | tableau                   | Liste des contacts de l'entreprise                                
contacts.name                   | chaîne de caractères      | Nom de la personne de contact                              
contacts.role                   | chaîne de caractères      | Rôle ou fonction du contact                         
nb_actes                        | entier                    | Nombre d'actes liés à l'entreprise

[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)

## Find list of companies

> The above command returns JSON structured like this:

```json
[
  {
    "cccid": "FR_519570196",
    "siren": "519570196",
    "siret_siege": "51957019600047",
    "type_etablissement": "siege",
    "raison_sociale": "NOVAWAY",
    "appartient_groupe": false,
    "adresse_complete": "13 rue Jules Valles 69100 VILLEURBANNE",
    "adresse_postale": "13 rue Jules Valles",
    "code_postal": "69100",
    "ville": "VILLEURBANNE",
    "last_modified": "2021-12-07T15:35:45",
    "sigle": null,
    "resume_activite": "développement de logiciels métiers, applications et plateformes web",
    "pays": "France",
    "radiee": false,
    "nbre_signaux": 1,
    "nbre_articles": 1,
    "logo_url": "https://pbs.twimg.com/profile_images/730069922391465984/iosvIlkK_400x400.jpg",
    "links\"": [
      {
        "rel": "self",
        "href": "https://decidentov2.local-centos7.com/companies/FR_519570196"
      },
      {
        "rel": "extranet",
        "href": "https://decidentov2.local-centos7.com/app_dev.php/extranet/company/infoplusV2/FR_519570196"
      }
    ]
  }
]
```

This endpoint retrieves some company by its ID.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/companies/v2`

### Query Parameters

Champ                     | Type                     | Description                                                      
--------------------------|--------------------------|-------------------------------------------------------------------
siren                     | Entier                   | Identifiant SIREN unique                                       
|                          | Valeur exemple : 327888111                                     
siret                     | Entier                   | Identifiant SIRET unique                                       
|                          | Valeur exemple : 32788811100447                                 
term                      | Chaîne de caractères     | Terme de recherche                                             
|                          | Valeur exemple : CEGID                                         
code_postal              | Chaîne de caractères     | Code postal                                                   
|                          | Valeur exemple : 69009                                         
ville                     | Chaîne de caractères     | Ville                                                          
|                          | Valeur exemple : Lyon                                          
pays                      | Chaîne de caractères     | Pays                                                          
|                          | Valeur exemple : France                                        
naf                       | Chaîne de caractères     | Code APE des entreprises                                       
|                          | Valeur exemple : 70.10Z                                       
radiee                    | Entier                   | Indique si l'entreprise est radiée (1 pour oui)                
|                          | Valeur par défaut : null                                       
|                          | Valeur exemple : 1                                             
appartient_groupe        | Entier                   | Indique si l'entreprise appartient à un groupe (1 pour oui)    
|                          | Valeur par défaut : null                                       
|                          | Valeur exemple : 1                                             
derniere_maj             | Date                     | Date de dernière mise à jour (plus grande que cette date)       
|                          | Valeur exemple : 2021-11-12                                   
limit                     | Entier                   | Nombre maximum d'entreprises à retourner                        
|                          | Valeur par défaut : 100                                       
|                          | Valeur exemple : 100                                           
offset                    | Entier                   | Numéro de départ pour les entreprises retournées (utilisé pour la pagination)  
|                          | Valeur par défaut : 1                                         
|                          | Valeur exemple : 100                                           
order                     | Chaîne de caractères     | Champ d'ordre pour les résultats                                 
|                          | Valeurs disponibles : raison_sociale_keyword, last_kpi.ca_bilan, last_kpi.effectif, cccid, last_modified  
|                          | Valeur par défaut : last_modified                               
sort                      | Chaîne de caractères     | Direction de tri (desc ou asc)                                  
|                          | Valeurs disponibles : desc, asc                                 
|                          | Valeur par défaut : desc                                       
meta                      | Booléen                  | Sortie des informations de pagination (false par défaut)        
|                          | Valeur par défaut : false                                       
_format                  | Chaîne de caractères     | Format de sortie (json ou xml)                                   
|                          | Valeurs disponibles : json, xml                                 
|                          | Valeur par défaut : json                                       




### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

[//]: # (c'est une répétition par rapport au precedentes responses)

Champ                     | Type                     | Description                                                      
--------------------------|--------------------------|-------------------------------------------------------------------
cccid                     | Chaîne de caractères     | Identifiant CCCID de l'entreprise
siren                     | Chaîne de caractères     | Identifiant SIREN de l'entreprise
siret_siege               | Chaîne de caractères     | Identifiant SIRET du siège social de l'entreprise
type_etablissement        | Chaîne de caractères     | Type d'établissement (par exemple : siège)
raison_sociale            | Chaîne de caractères     | Raison sociale de l'entreprise
appartient_groupe         | Booléen                  | Indique si l'entreprise appartient à un groupe (false pour non)  
adresse_complete          | Chaîne de caractères     | Adresse complète de l'entreprise
adresse_postale           | Chaîne de caractères     | Adresse postale de l'entreprise              
code_postal              | Chaîne de caractères     | Code postal de l'entreprise
ville                     | Chaîne de caractères     | Ville où se situe l'entreprise
last_modified             | Date                     | Date de dernière modification
sigle                     | Chaîne de caractères     | Sigle de l'entreprise (null si non applicable)
resume_activite           | Chaîne de caractères     | Résumé de l'activité de l'entreprise
pays                      | Chaîne de caractères     | Pays où se situe l'entreprise
radiee                    | Booléen                  | Indique si l'entreprise est radiée (false pour non)            
nbre_signaux             | Entier                   | Nombre de signaux associés à l'entreprise
nbre_articles             | Entier                   | Nombre d'articles associés à l'entreprise
logo_url                 | Chaîne de caractères     | URL du logo de l'entreprise
links                    | Liste d'objets          | Liens associés à l'entreprise                                    

[//]: # (|                          | Valeur exemple : <a> https://decidentov2.local-centos7.com/companies/FR_519570196 </a>)




[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)


