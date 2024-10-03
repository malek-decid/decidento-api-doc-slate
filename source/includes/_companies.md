# Companies

L'API "Companies" permet de rechercher et de récupérer des informations détaillées sur des sociétés à partir de plusieurs types d'identifiants et de paramètres. Voici les principales routes disponibles :

- **<span class="method-get">GET</span> [/companies](#get-all-companies)** : Recherche de sociétés en utilisant divers paramètres de recherche.
- **<span class="method-get">GET</span> [/companies/{companyId}](#find-company-by-id)** : Récupère les détails d'une société spécifique à partir de son identifiant unique (ID).
- **<span class="method-get">GET</span> [/companies/collection](#find-list-of-companies-by-ids)** : Récupère une collection de sociétés en fournissant une liste d'IDs.
- **<span class="method-get">GET</span> [/companies/v2](#find-list-of-companies)** : Nouvelle version pour la recherche de sociétés avec des paramètres avancés.
- **<span class="method-get">GET</span> [/companies/{companyCccid}/v2](#find-company-by-its-unique-identifier-cccid)** : Trouve une société en utilisant son identifiant unique CCCID.
- **<span class="method-get">GET</span> [/companies/collection/v2](#find-a-collection-of-companies-by-their-siren)** : Récupère une collection de sociétés en fournissant une liste de numéros SIREN.

Consultez ce lien pour tester : <a href="https://api.decidento.com/documentation/" target="_blank" rel="noopener noreferrer">API Decidento</a>.


## Get All Companies

> This query returns JSON structured like this:

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

This endpoint retrieves all companies according to the query parameters shown below.

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
| **sirets**       | Tableau[]             | Liste des SIRET de l'entreprise avec leurs types                                             |
| &nbsp;&nbsp;&nbsp;sirets.siret     | Entier                | Numéro SIRET associé à l'entreprise                                                           |
| &nbsp;&nbsp;&nbsp;sirets.type      | Entier                | Type associé au SIRET                                                                          |
| **links**        | Tableau[]             | Liste des liens associés à l'entreprise                                                       |
| &nbsp;&nbsp;&nbsp;links.rel        | Chaîne de caractères   | Relation du lien                                                                                |
| &nbsp;&nbsp;&nbsp;links.href       | Chaîne de caractères   | URL du lien                                                                                   |

[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## Find Company by ID

> This query returns JSON structured like this:

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

This endpoint retrieves a company by its ID.

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

| Field                          | Type                      | Description                                             |
|--------------------------------|---------------------------|---------------------------------------------------------|
| id                             | entier                    | Identifiant unique de l'entreprise                      |
| siren                          | entier                    | Numéro SIREN (identifiant unique à 9 chiffres)         |
| siret                          | entier                    | Numéro SIRET (identifiant de l’établissement à 14 chiffres) |
| siege                          | booléen                   | Indique si c'est le siège social                        |
| social_name                    | chaîne de caractères      | Raison sociale de l'entreprise                           |
| **sirets**                     | tableau                   | Liste des numéros SIRET associés                        |
| &nbsp;&nbsp;&nbsp;sirets.siret | entier                    | Numéro SIRET de l'établissement                        |
| &nbsp;&nbsp;&nbsp;sirets.type  | entier                    | Code de type de l'établissement                         |
| **links**                      | tableau                   | Liste des liens associés                                 |
| &nbsp;&nbsp;&nbsp;links.rel    | chaîne de caractères      | Type de relation                                        |
| &nbsp;&nbsp;&nbsp;links.href   | chaîne de caractères      | URL vers les informations de l'entreprise               |
| last_modified                  | chaîne de caractères (date-heure) | Date de dernière modification des informations de l'entreprise |
| enseigne                       | chaîne de caractères      | Nom commercial de l'entreprise                           |
| sigle                          | chaîne de caractères      | Sigle de l'entreprise                                   |
| rcs                            | chaîne de caractères      | Numéro d’immatriculation au registre du commerce et des sociétés (RCS) |
| tva_number                     | chaîne de caractères      | Numéro de TVA                                          |
| index_euro                     | entier                    | Indice européen pour les informations de l'entreprise   |
| immatriculation_date           | chaîne de caractères (date) | Date d’immatriculation                                  |
| naf_code                       | chaîne de caractères      | Code NAF et description de l'activité                   |
| juridic_form                   | chaîne de caractères      | Forme juridique de l'entreprise                         |
| type_etablissement             | chaîne de caractères      | Type d'établissement                                    |
| categorie_full                 | chaîne de caractères      | Description complète de la catégorie                    |
| category_light                 | chaîne de caractères      | Description légère de la catégorie                      |
| capital_social                 | entier                    | Capital social de l'entreprise                          |
| fonds_propres                  | entier                    | Fonds propres                                          |
| ca_bilan                       | entier                    | Chiffre d’affaires selon le bilan                       |
| effectif_precis                | entier                    | Nombre précis d’employés                                |
| resultat_net                   | entier                    | Résultat net                                           |
| resultat_exploitation          | entier                    | Résultat d'exploitation                                 |
| radiate                        | booléen                   | Indique si l'entreprise est radiée                      |
| indice_risque_info_legal       | chaîne de caractères      | Indice de risque légal                                  |
| indice_risque_score3           | entier                    | Score de risque selon Score3                            |
| anne_indice_risque_score3      | entier                    | Année du score de risque Score3                         |
| nb_filliales_directes          | entier                    | Nombre de filiales directes                             |
| nb_filliales_indirectes        | entier                    | Nombre de filiales indirectes                           |
| address                        | chaîne de caractères      | Adresse complète                                        |
| zip                            | chaîne de caractères      | Code postal                                            |
| city                           | chaîne de caractères      | Ville                                                  |
| department                     | chaîne de caractères      | Département                                            |
| country                        | chaîne de caractères      | Pays                                                   |
| geo_lat                        | nombre à virgule flottante| Latitude géographique                                   |
| geo_long                       | nombre à virgule flottante| Longitude géographique                                  |
| telephone_number               | chaîne de caractères      | Numéro de téléphone                                     |
| fax_number                     | chaîne de caractères      | Numéro de fax                                          |
| web_site                       | chaîne de caractères      | URL du site web                                        |
| url_maps                       | chaîne de caractères      | URL de la localisation sur Google Maps                  |
| url_viadeo                     | chaîne de caractères      | URL du profil Viadeo (si disponible)                   |
| url_twitter                    | chaîne de caractères      | URL du profil Twitter (si disponible)                  |
| url_gnews                      | chaîne de caractères      | URL vers Google News (si disponible)                   |
| url_wikipedia                  | chaîne de caractères      | URL de la page Wikipédia (si disponible)               |
| url_facebook                   | chaîne de caractères      | URL du profil Facebook (si disponible)                 |
| url_linkedin                   | chaîne de caractères      | URL du profil LinkedIn (si disponible)                 |
| url_score3                     | chaîne de caractères      | URL du profil Score3                                   |
| url_scoopit                    | chaîne de caractères      | URL du profil Scoop.it (si disponible)                 |
| logo_url                       | chaîne de caractères      | URL du logo de l'entreprise                             |
| email_contact                  | chaîne de caractères      | Adresse e-mail de contact                               |
| **contacts**                   | tableau                   | Liste des contacts de l'entreprise                      |
| &nbsp;&nbsp;&nbsp;contacts.name| chaîne de caractères      | Nom de la personne de contact                           |
| &nbsp;&nbsp;&nbsp;contacts.role| chaîne de caractères      | Rôle ou fonction du contact                             |
| nb_actes                       | entier                    | Nombre d'actes liés à l'entreprise                      |

[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## Find list of companies by IDs

> This query returns JSON structured like this:

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

This endpoint retrieves companies according to the query parameters shown below.

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

| Field                          | Type                      | Description                                             |
|--------------------------------|---------------------------|---------------------------------------------------------|
| id                             | entier                    | Identifiant unique de l'entreprise                      |
| siren                          | entier                    | Numéro SIREN (identifiant unique à 9 chiffres)         |
| siret                          | entier                    | Numéro SIRET (identifiant de l’établissement à 14 chiffres) |
| siege                          | booléen                   | Indique si c'est le siège social                        |
| social_name                    | chaîne de caractères      | Raison sociale de l'entreprise                           |
| **sirets**                     | tableau                   | Liste des numéros SIRET associés                        |
| &nbsp;&nbsp;&nbsp;sirets.siret | entier                    | Numéro SIRET de l'établissement                        |
| &nbsp;&nbsp;&nbsp;sirets.type  | entier                    | Code de type de l'établissement                         |
| **links**                      | tableau                   | Liste des liens associés                                 |
| &nbsp;&nbsp;&nbsp;links.rel    | chaîne de caractères      | Type de relation                                        |
| &nbsp;&nbsp;&nbsp;links.href   | chaîne de caractères      | URL vers les informations de l'entreprise               |
| last_modified                  | chaîne de caractères (date-heure) | Date de dernière modification des informations de l'entreprise |
| enseigne                       | chaîne de caractères      | Nom commercial de l'entreprise                           |
| sigle                          | chaîne de caractères      | Sigle de l'entreprise                                   |
| rcs                            | chaîne de caractères      | Numéro d’immatriculation au registre du commerce et des sociétés (RCS) |
| tva_number                     | chaîne de caractères      | Numéro de TVA                                          |
| index_euro                     | entier                    | Indice européen pour les informations de l'entreprise   |
| immatriculation_date           | chaîne de caractères (date) | Date d’immatriculation                                  |
| naf_code                       | chaîne de caractères      | Code NAF et description de l'activité                   |
| juridic_form                   | chaîne de caractères      | Forme juridique de l'entreprise                         |
| type_etablissement             | chaîne de caractères      | Type d'établissement                                    |
| categorie_full                 | chaîne de caractères      | Description complète de la catégorie                    |
| category_light                 | chaîne de caractères      | Description légère de la catégorie                      |
| capital_social                 | entier                    | Capital social de l'entreprise                          |
| fonds_propres                  | entier                    | Fonds propres                                          |
| ca_bilan                       | entier                    | Chiffre d’affaires selon le bilan                       |
| effectif_precis                | entier                    | Nombre précis d’employés                                |
| resultat_net                   | entier                    | Résultat net                                           |
| resultat_exploitation          | entier                    | Résultat d'exploitation                                 |
| radiate                        | booléen                   | Indique si l'entreprise est radiée                      |
| indice_risque_info_legal       | chaîne de caractères      | Indice de risque légal                                  |
| indice_risque_score3           | entier                    | Score de risque selon Score3                            |
| anne_indice_risque_score3      | entier                    | Année du score de risque Score3                         |
| nb_filliales_directes          | entier                    | Nombre de filiales directes                             |
| nb_filliales_indirectes        | entier                    | Nombre de filiales indirectes                           |
| address                        | chaîne de caractères      | Adresse complète                                        |
| zip                            | chaîne de caractères      | Code postal                                            |
| city                           | chaîne de caractères      | Ville                                                  |
| department                     | chaîne de caractères      | Département                                            |
| country                        | chaîne de caractères      | Pays                                                   |
| geo_lat                        | nombre à virgule flottante| Latitude géographique                                   |
| geo_long                       | nombre à virgule flottante| Longitude géographique                                  |
| telephone_number               | chaîne de caractères      | Numéro de téléphone                                     |
| fax_number                     | chaîne de caractères      | Numéro de fax                                          |
| web_site                       | chaîne de caractères      | URL du site web                                        |
| url_maps                       | chaîne de caractères      | URL de la localisation sur Google Maps                  |
| url_viadeo                     | chaîne de caractères      | URL du profil Viadeo (si disponible)                   |
| url_twitter                    | chaîne de caractères      | URL du profil Twitter (si disponible)                  |
| url_gnews                      | chaîne de caractères      | URL vers Google News (si disponible)                   |
| url_wikipedia                  | chaîne de caractères      | URL de la page Wikipédia (si disponible)               |
| url_facebook                   | chaîne de caractères      | URL du profil Facebook (si disponible)                 |
| url_linkedin                   | chaîne de caractères      | URL du profil LinkedIn (si disponible)                 |
| url_score3                     | chaîne de caractères      | URL du profil Score3                                   |
| url_scoopit                    | chaîne de caractères      | URL du profil Scoop.it (si disponible)                 |
| logo_url                       | chaîne de caractères      | URL du logo de l'entreprise                             |
| email_contact                  | chaîne de caractères      | Adresse e-mail de contact                               |
| **contacts**                   | tableau                   | Liste des contacts de l'entreprise                      |
| &nbsp;&nbsp;&nbsp;contacts.name| chaîne de caractères      | Nom de la personne de contact                           |
| &nbsp;&nbsp;&nbsp;contacts.role| chaîne de caractères      | Rôle ou fonction du contact                             |
| nb_actes                       | entier                    | Nombre d'actes liés à l'entreprise                      |

[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)

## Find list of companies

> This query returns JSON structured like this:

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

| Champ                     | Type                     | Description                                                 |
|---------------------------|--------------------------|-------------------------------------------------------------|
| cccid                     | Chaîne de caractères     | Identifiant CCCID de l'entreprise                           |
| siren                     | Chaîne de caractères     | Identifiant SIREN de l'entreprise                           |
| siret_siege               | Chaîne de caractères     | Identifiant SIRET du siège social de l'entreprise          |
| type_etablissement        | Chaîne de caractères     | Type d'établissement (par exemple : siège)                 |
| raison_sociale            | Chaîne de caractères     | Raison sociale de l'entreprise                              |
| appartient_groupe         | Booléen                  | Indique si l'entreprise appartient à un groupe (false pour non) |
| adresse_complete           | Chaîne de caractères     | Adresse complète de l'entreprise                            |
| adresse_postale           | Chaîne de caractères     | Adresse postale de l'entreprise                             |
| code_postal               | Chaîne de caractères     | Code postal de l'entreprise                                 |
| ville                     | Chaîne de caractères     | Ville où se situe l'entreprise                              |
| last_modified             | Date                     | Date de dernière modification                               |
| sigle                     | Chaîne de caractères     | Sigle de l'entreprise (null si non applicable)            |
| resume_activite           | Chaîne de caractères     | Résumé de l'activité de l'entreprise                        |
| pays                      | Chaîne de caractères     | Pays où se situe l'entreprise                               |
| radiee                    | Booléen                  | Indique si l'entreprise est radiée (false pour non)       |
| nbre_signaux             | Entier                   | Nombre de signaux associés à l'entreprise                   |
| nbre_articles            | Entier                   | Nombre d'articles associés à l'entreprise                   |
| logo_url                 | Chaîne de caractères     | URL du logo de l'entreprise                                 |
| **links**                | Liste d'objets          | Liens associés à l'entreprise                               |

[//]: # (|                          | Valeur exemple : <a> https://decidentov2.local-centos7.com/companies/FR_519570196 </a>)




[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)

## Find company by its unique identifier CCCID

> This query returns JSON structured like this:

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
    "last_modified": null,
    "sigle": null,
    "resume_activite": "développement de logiciels métiers applications et plateformes web",
    "pays": "France",
    "radiee": false,
    "nbre_signaux": 0,
    "nbre_articles": 0,
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
    ],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/FR_519570196"
      },
      {
        "rel": "extranet",
        "href": "https://api.decidento.com/extranet/company/infoplusV2/FR_519570196"
      }
    ],
    "nombre_etablissements_secondaires_inactifs": 3,
    "nombre_etablissements_secondaires_actifs": 0,
    "caractere_employeur": true,
    "enseignes": null,
    "date_creation": "2010-01-05",
    "numero_tva": "FR43519570196",
    "telephone": "04 82 53 99 00",
    "departement_label": "Rhône",
    "departement": "69",
    "geo_lat": "45.769417",
    "geo_long": "4.864512",
    "code_ape": "62.01Z",
    "code_ape_brut": "6201Z",
    "code_ape_label": "Programmation informatique",
    "code_ape_complet": "6201Z - Programmation informatique",
    "forme_juridique_code": "5710",
    "forme_juridique": "SAS société par actions simplifiée",
    "type_entreprise": "PME",
    "site_ecommerce": false,
    "activite_rd": false,
    "activite_export": false,
    "cac40": false,
    "startup": false,
    "secteur_industriel": false,
    "entreprise_fintech": false,
    "entreprise_familiale": false,
    "entreprise_b2c": true,
    "entreprise_b2b": true,
    "entreprise_biotech_medtech": false,
    "website": null,
    "url_twitter": "https://twitter.com/@novaway",
    "url_facebook": "https://www.facebook.com/novawayfr/",
    "url_linkedin": "https://www.linkedin.com/company/novaway/",
    "email_contact": "contact@novaway.fr",
    "code_confidentialite": true,
    "avertissement_bilan": "les bilans étant confidentiels ou non disponibles nous ne pouvons afficher toutes les données chiffrées",
    "subventions_investissements": 123456789,
    "participation_bilan": 123456789,
    "resultat_bilan": 123456789,
    "resultat_net_consolide": 123456789,
    "dotations_amortissements": 123456789,
    "ca_consolide": 123456789,
    "resultat_exploitation": 123456789,
    "ca_bilan": 123456789,
    "impots_taxes": 123456789,
    "effectif_sous_traitance": 123456789,
    "charges_financieres": 123456789,
    "salaires_traitements": 123456789,
    "ca_export": 123456789,
    "ca_france": 123456789,
    "effectif": 10,
    "fonds_propres": 529033,
    "capital_social": 13500,
    "duree_exercice": 12,
    "annee_cloture_exercice": "2020",
    "date_cloture_exercice": "2020-12-31",
    "contacts": [
      {
        "type": "P.Physique",
        "name": "mr X",
        "first_name": "xxxx",
        "role": "Président"
      },
      {
        "type": "P.Physique",
        "name": "Miss Y",
        "role": "Directeur général",
        "first_name": "yyyy"
      }
    ]
  }
]
```

This endpoint retrieves a company by its unique identifier CCCID.

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

Champ           | Type               | Description                                                                              
----------------|--------------------|------------------------------------------------------------------------------------------
companyCccid *  | Chaîne de caractères | CCCID de l'entreprise à retourner (obligatoire)                                            
| Exemple : FR_327888111                                                                                        
_format         | Chaîne de caractères | Format de sortie                                                                         
|                    | Valeurs disponibles : json, xml                                                                                
|                    | Valeur par défaut : json


### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

[//]: # (c'est une répétition par rapport au precedentes responses)

| Champ                                                         | Type                        | Description                                                                                     |
|---------------------------------------------------------------|-----------------------------|-------------------------------------------------------------------------------------------------|
| cccid                                                         | Chaîne de caractères        | Code CCCID de l'entreprise (ex: FR_519570196)                                                 |
| siren                                                         | Chaîne de caractères        | Code SIREN de l'entreprise (ex: 519570196)                                                   |
| siret_siege                                                   | Chaîne de caractères        | Code SIRET du siège de l'entreprise (ex: 51957019600047)                                     |
| type_etablissement                                            | Chaîne de caractères        | Type d'établissement (ex: siège)                                                               |
| raison_sociale                                                | Chaîne de caractères        | Raison sociale de l'entreprise (ex: NOVAWAY)                                                  |
| appartient_groupe                                             | Booléen                     | Indique si l'entreprise appartient à un groupe (true/false)                                   |
| adresse_complete                                              | Chaîne de caractères        | Adresse complète de l'entreprise (ex: 13 rue Jules Valles 69100 VILLEURBANNE)                |
| adresse_postale                                              | Chaîne de caractères        | Adresse postale de l'entreprise (ex: 13 rue Jules Valles)                                     |
| code_postal                                                   | Chaîne de caractères        | Code postal de l'entreprise (ex: 69100)                                                       |
| ville                                                         | Chaîne de caractères        | Ville de l'entreprise (ex: VILLEURBANNE)                                                      |
| last_modified                                                 | Date                        | Date de la dernière modification (nullable)                                                    |
| sigle                                                         | Chaîne de caractères        | Sigle de l'entreprise (nullable)                                                                |
| resume_activite                                               | Chaîne de caractères        | Résumé de l'activité (ex: développement de logiciels métiers, applications et plateformes web) |
| pays                                                          | Chaîne de caractères        | Pays de l'entreprise (ex: France)                                                               |
| radiee                                                        | Booléen                     | Indique si l'entreprise est radiée (false)                                                    |
| nbre_signaux                                                 | Entier                      | Nombre de signaux (ex: 0)                                                                       |
| nbre_articles                                                | Entier                      | Nombre d'articles (ex: 0)                                                                        |
| logo_url                                                     | Chaîne de caractères        | URL du logo de l'entreprise                                                                      |
| links                                                         | Tableau                     | Liens relatifs (ex: self, extranet)                                                            |
| nombre_etablissements_secondaires_inactifs                   | Entier                      | Nombre d'établissements secondaires inactifs (ex: 3)                                          |
| nombre_etablissements_secondaires_actifs                     | Entier                      | Nombre d'établissements secondaires actifs (ex: 0)                                            |
| caractere_employeur                                          | Booléen                     | Indique si l'entreprise a un caractère employeur (true/false)                                  |
| enseignes                                                    | Chaîne de caractères        | Enseignes associées (nullable)                                                                   |
| date_creation                                                | Date                        | Date de création de l'entreprise (ex: 2010-01-05)                                             |
| numero_tva                                                   | Chaîne de caractères        | Numéro de TVA intracommunautaire (ex: FR43519570196)                                         |
| telephone                                                    | Chaîne de caractères        | Numéro de téléphone de l'entreprise (ex: 04 82 53 99 00)                                      |
| departement_label                                            | Chaîne de caractères        | Libellé du département (ex: Rhône)                                                              |
| departement                                                  | Chaîne de caractères        | Code du département (ex: 69)                                                                    |
| geo_lat                                                      | Chaîne de caractères        | Latitude géographique (ex: 45.769417)                                                          |
| geo_long                                                     | Chaîne de caractères        | Longitude géographique (ex: 4.864512)                                                          |
| code_ape                                                     | Chaîne de caractères        | Code APE de l'entreprise (ex: 62.01Z)                                                          |
| code_ape_label                                               | Chaîne de caractères        | Libellé du code APE (ex: Programmation informatique)                                           |
| forme_juridique_code                                         | Chaîne de caractères        | Code de la forme juridique (ex: 5710)                                                          |
| forme_juridique                                             | Chaîne de caractères        | Forme juridique (ex: SAS société par actions simplifiée)                                        |
| type_entreprise                                              | Chaîne de caractères        | Type d'entreprise (ex: PME)                                                                      |
| site_ecommerce                                               | Booléen                     | Indique si l'entreprise a un site e-commerce (true/false)                                      |
| activite_rd                                                 | Booléen                     | Indique si l'entreprise a une activité de R&D (true/false)                                     |
| activite_export                                             | Booléen                     | Indique si l'entreprise fait de l'export (true/false)                                          |
| cac40                                                        | Booléen                     | Indique si l'entreprise est membre du CAC 40 (false)                                          |
| startup                                                      | Booléen                     | Indique si l'entreprise est une startup (false)                                               |
| secteur_industriel                                          | Booléen                     | Indique si l'entreprise appartient au secteur industriel (false)                               |
| entreprise_fintech                                          | Booléen                     | Indique si l'entreprise est une fintech (false)                                               |
| entreprise_familiale                                        | Booléen                     | Indique si l'entreprise est une entreprise familiale (false)                                   |
| entreprise_b2c                                             | Booléen                     | Indique si l'entreprise est orientée B2C (true/false)                                         |
| entreprise_b2b                                             | Booléen                     | Indique si l'entreprise est orientée B2B (true/false)                                         |
| entreprise_biotech_medtech                                 | Booléen                     | Indique si l'entreprise est une biotech ou medtech (false)                                   |
| website                                                     | Chaîne de caractères        | URL du site web (nullable)                                                                         |
| url_twitter                                                 | Chaîne de caractères        | URL du compte Twitter (ex: https://twitter.com/@novaway)                                       |
| url_facebook                                                | Chaîne de caractères        | URL de la page Facebook (ex: https://www.facebook.com/novawayfr/)                             |
| url_linkedin                                                | Chaîne de caractères        | URL du profil LinkedIn (ex: https://www.linkedin.com/company/novaway/)                        |
| email_contact                                                | Chaîne de caractères        | Email de contact (ex: contact@novaway.fr)                                                       |
| code_confidentialite                                         | Booléen                     | Code de confidentialité (true/false)                                                              |
| avertissement_bilan                                          | Chaîne de caractères        | Avertissement sur les bilans                                                                       |
| subventions_investissements                                  | Entier                      | Subventions et investissements (ex: 123456789)                                                  |
| participation_bilan                                          | Entier                      | Participation au bilan (ex: 123456789)                                                          |
| resultat_bilan                                              | Entier                      | Résultat du bilan (ex: 123456789)                                                                |
| resultat_net_consolide                                       | Entier                      | Résultat net consolidé (ex: 123456789)                                                           |
| dotations_amortissements                                     | Entier                      | Dotations aux amortissements (ex: 123456789)                                                   |
| ca_consolide                                                | Entier                      | Chiffre d'affaires consolidé (ex: 123456789)                                                   |
| resultat_exploitation                                        | Entier                      | Résultat d'exploitation (ex: 123456789)                                                          |
| ca_bilan                                                    | Entier                      | Chiffre d'affaires du bilan (ex: 123456789)                                                     |
| impots_taxes                                                | Entier                      | Montant des impôts et taxes (ex: 123456789)                                                     |
| effectif_sous_traitance                                     | Entier                      | Effectif sous-traitance (ex: 123456789)                                                         |
| charges_financieres                                         | Entier                      | Charges financières (ex: 123456789)                                                              |
| salaires_traitements                                         | Entier                      | Salaires et traitements (ex: 123456789)                                                          |
| ca_export                                                   | Entier                      | Chiffre d'affaires à l'export (ex: 123456789)                                                   |
| ca_france                                                   | Entier                      | Chiffre d'affaires en France (ex: 123456789)                                                    |
| effectif                                                    | Entier                      | Effectif total de l'entreprise (ex: 10)                                                          |
| fonds_propres                                               | Entier                      | Fonds propres de l'entreprise (ex: 529033)                                                       |
| capital_social                                              | Entier                      | Capital social de l'entreprise (ex: 13500)                                                      |
| duree_exercice                                              | Entier                      | Durée de l'exercice (en mois, ex: 12)                                                            |
| annee_cloture_exercice                                      | Année                       | Année de clôture de l'exercice (ex: 2020)                                                        |
| date_cloture_exercice                                       | Date                        | Date de clôture de l'exercice (ex: 2020-12-31)                                                  |
| contacts                                                    | Tableau                    | Liste des contacts de l'entreprise (type, nom, prénom, rôle)                                    |



[//]: # (|                          | Valeur exemple : <a> https://decidentov2.local-centos7.com/companies/FR_519570196 </a>)

[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)

## Find a collection of companies by their SIREN

> This query returns JSON structured like this:

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
    "last_modified": null,
    "sigle": null,
    "resume_activite": "développement de logiciels métiers applications et plateformes web",
    "pays": "France",
    "radiee": false,
    "nbre_signaux": 0,
    "nbre_articles": 0,
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
    ],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/FR_519570196"
      },
      {
        "rel": "extranet",
        "href": "https://api.decidento.com/extranet/company/infoplusV2/FR_519570196"
      }
    ],
    "nombre_etablissements_secondaires_inactifs": 3,
    "nombre_etablissements_secondaires_actifs": 0,
    "caractere_employeur": true,
    "enseignes": null,
    "date_creation": "2010-01-05",
    "numero_tva": "FR43519570196",
    "telephone": "04 82 53 99 00",
    "departement_label": "Rhône",
    "departement": "69",
    "geo_lat": "45.769417",
    "geo_long": "4.864512",
    "code_ape": "62.01Z",
    "code_ape_brut": "6201Z",
    "code_ape_label": "Programmation informatique",
    "code_ape_complet": "6201Z - Programmation informatique",
    "forme_juridique_code": "5710",
    "forme_juridique": "SAS société par actions simplifiée",
    "type_entreprise": "PME",
    "site_ecommerce": false,
    "activite_rd": false,
    "activite_export": false,
    "cac40": false,
    "startup": false,
    "secteur_industriel": false,
    "entreprise_fintech": false,
    "entreprise_familiale": false,
    "entreprise_b2c": true,
    "entreprise_b2b": true,
    "entreprise_biotech_medtech": false,
    "website": null,
    "url_twitter": "https://twitter.com/@novaway",
    "url_facebook": "https://www.facebook.com/novawayfr/",
    "url_linkedin": "https://www.linkedin.com/company/novaway/",
    "email_contact": "contact@novaway.fr",
    "code_confidentialite": true,
    "avertissement_bilan": "les bilans étant confidentiels ou non disponibles nous ne pouvons afficher toutes les données chiffrées",
    "subventions_investissements": 123456789,
    "participation_bilan": 123456789,
    "resultat_bilan": 123456789,
    "resultat_net_consolide": 123456789,
    "dotations_amortissements": 123456789,
    "ca_consolide": 123456789,
    "resultat_exploitation": 123456789,
    "ca_bilan": 123456789,
    "impots_taxes": 123456789,
    "effectif_sous_traitance": 123456789,
    "charges_financieres": 123456789,
    "salaires_traitements": 123456789,
    "ca_export": 123456789,
    "ca_france": 123456789,
    "effectif": 10,
    "fonds_propres": 529033,
    "capital_social": 13500,
    "duree_exercice": 12,
    "annee_cloture_exercice": "2020",
    "date_cloture_exercice": "2020-12-31",
    "contacts": [
      {
        "type": "P.Physique",
        "name": "mr X",
        "first_name": "xxxx",
        "role": "Président"
      },
      {
        "type": "P.Physique",
        "name": "Miss Y",
        "role": "Directeur général",
        "first_name": "yyyy"
      }
    ]
  }
]
```

This endpoint retrieves a list of companies by SIREN.

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

Champ         | Type            | Description                         
--------------|-----------------|-------------------------------------
listIds *     | Tableau[entier] | Tableau contenant les SIREN des entreprises à retourner


### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

[//]: # (c'est une répétition par rapport au precedentes responses)

Champ                                   | Type                  | Description                                                                          
----------------------------------------|-----------------------|--------------------------------------------------------------------------------------
cccid                                   | Chaîne de caractères  | Code CCCID de l'entreprise (ex: FR_519570196)                                         
siren                                   | Chaîne de caractères  | Code SIREN de l'entreprise (ex: 519570196)                                            
siret_siege                             | Chaîne de caractères  | Code SIRET du siège de l'entreprise (ex: 51957019600047)                              
type_etablissement                      | Chaîne de caractères  | Type d'établissement (ex: siege)                                                      
raison_sociale                          | Chaîne de caractères  | Raison sociale de l'entreprise (ex: NOVAWAY)                                          
appartient_groupe                       | Booléen               | Indique si l'entreprise appartient à un groupe (true/false)                           
adresse_complete                        | Chaîne de caractères  | Adresse complète de l'entreprise (ex: 13 rue Jules Valles 69100 VILLEURBANNE)         
adresse_postale                         | Chaîne de caractères  | Adresse postale de l'entreprise (ex: 13 rue Jules Valles)                             
code_postal                             | Chaîne de caractères  | Code postal de l'entreprise (ex: 69100)                                               
ville                                   | Chaîne de caractères  | Ville de l'entreprise (ex: VILLEURBANNE)                                              
last_modified                           | Date                  | Date de la dernière modification (nullable)                                           
sigle                                   | Chaîne de caractères  | Sigle de l'entreprise (nullable)                                                      
resume_activite                         | Chaîne de caractères  | Résumé de l'activité (ex: développement de logiciels métiers, applications et plateformes web)  
pays                                    | Chaîne de caractères  | Pays de l'entreprise (ex: France)                                                     
radiee                                  | Booléen               | Indique si l'entreprise est radiée (false)                                            
nbre_signaux                            | Entier                | Nombre de signaux (ex: 0)                                                             
nbre_articles                           | Entier                | Nombre d'articles (ex: 0)                                                             
logo_url                                | Chaîne de caractères  | URL du logo de l'entreprise                                                           
links                                   | Tableau               | Liens relatifs (ex: self, extranet)                                                   
nombre_etablissements_secondaires_inactifs | Entier              | Nombre d'établissements secondaires inactifs (ex: 3)                                  
nombre_etablissements_secondaires_actifs  | Entier              | Nombre d'établissements secondaires actifs (ex: 0)                                    
caractere_employeur                     | Booléen               | Indique si l'entreprise a un caractère employeur (true/false)                         
enseignes                               | Chaîne de caractères  | Enseignes associées (nullable)                                                        
date_creation                           | Date                  | Date de création de l'entreprise (ex: 2010-01-05)                                     
numero_tva                              | Chaîne de caractères  | Numéro de TVA intracommunautaire (ex: FR43519570196)                                  
telephone                               | Chaîne de caractères  | Numéro de téléphone de l'entreprise (ex: 04 82 53 99 00)                              
departement_label                       | Chaîne de caractères  | Libellé du département (ex: Rhône)                                                    
departement                             | Chaîne de caractères  | Code du département (ex: 69)                                                          
geo_lat                                 | Chaîne de caractères  | Latitude géographique (ex: 45.769417)                                                 
geo_long                                | Chaîne de caractères  | Longitude géographique (ex: 4.864512)                                                 
code_ape                                | Chaîne de caractères  | Code APE de l'entreprise (ex: 62.01Z)                                                 
code_ape_label                          | Chaîne de caractères  | Libellé du code APE (ex: Programmation informatique)                                  
forme_juridique_code                    | Chaîne de caractères  | Code de la forme juridique (ex: 5710)                                                 
forme_juridique                         | Chaîne de caractères  | Forme juridique (ex: SAS société par actions simplifiée)                              
type_entreprise                         | Chaîne de caractères  | Type d'entreprise (ex: PME)                                                           
site_ecommerce                          | Booléen               | Indique si l'entreprise a un site e-commerce (true/false)                             
activite_rd                             | Booléen               | Indique si l'entreprise a une activité de R&D (true/false)                            
activite_export                         | Booléen               | Indique si l'entreprise fait de l'export (true/false)                                 
cac40                                   | Booléen               | Indique si l'entreprise est membre du CAC 40 (false)                                  
startup                                 | Booléen               | Indique si l'entreprise est une startup (false)                                       
secteur_industriel                      | Booléen               | Indique si l'entreprise appartient au secteur industriel (false)                      
entreprise_fintech                      | Booléen               | Indique si l'entreprise est une fintech (false)                                       
entreprise_familiale                    | Booléen               | Indique si l'entreprise est une entreprise familiale (false)                          
entreprise_b2c                          | Booléen               | Indique si l'entreprise est orientée B2C (true/false)                                 
entreprise_b2b                          | Booléen               | Indique si l'entreprise est orientée B2B (true/false)                                 
entreprise_biotech_medtech              | Booléen               | Indique si l'entreprise est une biotech ou medtech (false)                            
website                                 | Chaîne de caractères  | URL du site web (nullable)                                                            
url_twitter                             | Chaîne de caractères  | URL du compte Twitter (ex: https://twitter.com/@novaway)                              
url_facebook                            | Chaîne de caractères  | URL de la page Facebook (ex: https://www.facebook.com/novawayfr/)                     
url_linkedin                            | Chaîne de caractères  | URL du profil LinkedIn (ex: https://www.linkedin.com/company/novaway/)                
email_contact                           | Chaîne de caractères  | Email de contact (ex: contact@novaway.fr)                                             
code_confidentialite                    | Booléen               | Code de confidentialité (true/false)                                                  
avertissement_bilan                     | Chaîne de caractères  | Avertissement sur les bilans                                                          
subventions_investissements             | Entier                | Subventions et investissements (ex: 123456789)                                        
participation_bilan                     | Entier                | Participation au bilan (ex: 123456789)                                                
resultat_bilan                          | Entier                | Résultat du bilan (ex: 123456789)                                                     
resultat_net_consolide                  | Entier                | Résultat net consolidé (ex: 123456789)                                                
dotations_amortissements                | Entier                | Dotations aux amortissements (ex: 123456789)                                          
ca_consolide                            | Entier                | Chiffre d'affaires consolidé (ex: 123456789)                                          
resultat_exploitation                   | Entier                | Résultat d'exploitation (ex: 123456789)                                               
ca_bilan                                | Entier                | Chiffre d'affaires du bilan (ex: 123456789)                                           
impots_taxes                            | Entier                | Montant des impôts et taxes (ex: 123456789)                                           
effectif_sous_traitance                 | Entier                | Effectif sous-traitance (ex: 123456789)                                               
charges_financieres                     | Entier                | Charges financières (ex: 123456789)                                                   
salaires_traitements                    | Entier                | Salaires et traitements (ex: 123456789)                                               
ca_export                               | Entier                | Chiffre d'affaires à l'export (ex: 123456789)                                         
ca_france                               | Entier                | Chiffre d'affaires en France (ex: 123456789)                                          
effectif                                | Entier                | Effectif total de l'entreprise (ex: 10)                                               
fonds_propres                           | Entier                | Fonds propres de l'entreprise (ex: 529033)                                            
capital_social                          | Entier                | Capital social de l'entreprise (ex: 13500)                                            
duree_exercice                          | Entier                | Durée de l'exercice (en mois, ex: 12)                                                 
annee_cloture_exercice                  | Année                 | Année de clôture de l'exercice (ex: 2020)                                             
date_cloture_exercice                   | Date                  | Date de clôture de l'exercice (ex: 2020-12-31)                                        
contacts                                | Tableau               | Liste des contacts de l'entreprise (type, nom, prénom, rôle)



[//]: # (|                          | Valeur exemple : <a> https://decidentov2.local-centos7.com/companies/FR_519570196 </a>)

[//]: # (<aside class="success">)

[//]: # (Remember!)

[//]: # (</aside>)


