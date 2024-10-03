# Signals

L'API "Signals" permet de récupérer des signaux d'activité liés aux sociétés et de consulter des collections de signaux spécifiques. Voici les principales routes :

- **<span class="method-get">GET</span> [/signals](#get-last-signals)** : Récupère les derniers signaux disponibles.
- **<span class="method-get">GET</span> [/signals/{signalId}]()** : Trouve un signal spécifique à partir de son identifiant unique (ID).
- **<span class="method-get">GET</span> [/signals/collection]()** : Récupère une collection de signaux en fournissant une liste d'IDs.

Consultez ce lien pour tester : <a href="https://api.decidento.com/documentation/" target="_blank" rel="noopener noreferrer">API Decidento</a>

## Get last signals

> This query returns JSON structured like this:

```json
[
  {
    "id": 1118256,
    "type": [
      {
        "id": 2,
        "code": "B",
        "label": "Construction"
      }
    ],
    "status": "Détecté",
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/signals/1118256"
      }
    ],
    "departments_list": [
      {
        "code": "26",
        "dep": "Drôme",
        "region": "Auvergne-Rhône-Alpes"
      }
    ],
    "last_article_pubdate": "21/01/2023",
    "creation_date": "21/01/2023",
    "last_update": "03/10/2024"
  },
  {
    "id": 1118259,
    "type": [
      {
        "id": 1,
        "code": "A",
        "label": "Aménagement & urbanisme"
      }
    ],
    "status": "Détecté",
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/signals/1118259"
      }
    ],
    "departments_list": [
      {
        "code": "22",
        "dep": "Côtes d'Armor",
        "region": "Bretagne"
      }
    ],
    "last_article_pubdate": "29/09/2024",
    "creation_date": "29/09/2024",
    "last_update": "03/10/2024"
  }
]
```

This endpoint retrieves a list of signals according to the query parameters shown below.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`
 https://api.decidento.com/signals/
`

### Query Parameters

Champ       | Type     | Description                                                              | Valeur par défaut
------------|----------|--------------------------------------------------------------------------|-----------------
limit       | Entier   | Limite des valeurs à considérer pour le filtrage                         | 200
offset      | Entier   | Début de l'offset (à combiner avec limit pour la pagination)             | 1
order       | Chaîne   | Champ d'ordonnancement                                                   | updatedAt
|          | Valeurs disponibles : updatedAt, publishedAt                            |
sort        | Chaîne   | Direction du tri                                                         | desc
|          | Valeurs disponibles : desc, asc                                          |
meta        | Booléen  | Informations paginées en sortie                                          | false
_format     | Chaîne   | Format de sortie                                                         | json
|          | Valeurs disponibles : json, xml                                          |

### Response (2 signals)

| Champ                                   | Type                        | Description                                                                                      |
|-----------------------------------------|-----------------------------|--------------------------------------------------------------------------------------------------|
| id                                      | Entier                      | Identifiant unique du signal.                                                                    |
| type                                    | Tableau                     | Type d'activité associée au signal.                                                              |
| &nbsp;&nbsp;&nbsp;&nbsp;- id            | Entier                      | Identifiant du type (ex: 2).                                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;- code          | Chaîne de caractères        | Code du type (ex: B).                                                                             |
| &nbsp;&nbsp;&nbsp;&nbsp;- label         | Chaîne de caractères        | Libellé du type (ex: Construction).                                                               |
| status                                  | Chaîne de caractères        | Statut du signal (ex: Détecté).                                                                  |
| links                                   | Tableau                     | Liens associés au signal.                                                                          |
| &nbsp;&nbsp;&nbsp;&nbsp;- rel           | Chaîne de caractères        | Relation du lien (ex: self).                                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;- href          | Chaîne de caractères        | URL du lien (ex: https://api.decidento.com/signals/1118256).                                    |
| departments_list                        | Tableau                     | Liste des départements associés au signal.                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;- code          | Chaîne de caractères        | Code du département (ex: 26).                                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;- dep           | Chaîne de caractères        | Nom du département (ex: Drôme).                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;- region        | Chaîne de caractères        | Région associée (ex: Auvergne-Rhône-Alpes).                                                     |
| last_article_pubdate                   | Date                        | Date de publication du dernier article lié au signal (ex: 21/01/2023).                          |
| creation_date                          | Date                        | Date de création du signal (ex: 21/01/2023).                                                    |
| last_update                            | Date                        | Date de la dernière mise à jour du signal (ex: 03/10/2024).                                     |


## Get a signal by ID

> This query returns JSON structured like this :

```json
{
  "id": 1000000,
  "departments_list": [
    {
      "code": "64",
      "dep": "Pyrénées Atlantiques",
      "region": "Nouvelle Aquitaine"
    }
  ],
  "last_article_pubdate": "04/04/2024",
  "creation_date": "03/04/2024",
  "last_update": "03/04/2024",
  "articles": [
    {
      "id": 756220,
      "title": "Interruption de la production à Mont pour Vertex Bioenergie",
      "pub_date": "04/04/2024",
      "links": [
        {
          "rel": "self",
          "href": "https://api.decidento.com/articles/756220"
        },
        {
          "rel": "extranet",
          "href": "https://platform.decidento.com/extranet/article/756220"
        }
      ]
    }
  ],
  "follow_date": null,
  "type": "K1",
  "label_type": "Investissements",
  "status": "Détecté",
  "company_main": {
    "id": 24531,
    "siren": "481741841",
    "siret": "48174184100037",
    "cccid": "FR_481741841",
    "social_name": "BIOENERGIE DU SUD-OUEST",
    "siege": true,
    "type": "main",
    "sirets": [],
    "links": [
      {
        "rel": "self",
        "href": "https://api.decidento.com/companies/24531"
      },
      {
        "rel": "self-v2",
        "href": "https://api.decidento.com/companies/FR_481741841/v2"
      },
      {
        "rel": "extranet",
        "href": "https://platform.decidento.com/extranet/company/infoplus/24531"
      },
      {
        "rel": "extranet-v2",
        "href": "https://platform.decidento.com/extranet/company/infoplusV2/FR_481741841"
      }
    ],
    "self_link": "https://api.decidento.com/companies/24531",
    "self_v2_link": "https://api.decidento.com/companies/FR_481741841/v2",
    "extranet_link": "https://platform.decidento.com/extranet/company/infoplus/24531",
    "extranet_v2_link": "https://platform.decidento.com/extranet/company/infoplusV2/FR_481741841"
  },
  "companies": [
    {
      "id": 24531,
      "siren": "481741841",
      "siret": "48174184100037",
      "cccid": "FR_481741841",
      "social_name": "BIOENERGIE DU SUD-OUEST",
      "siege": true,
      "type": "main",
      "sirets": [],
      "links": [
        {
          "rel": "self",
          "href": "https://api.decidento.com/companies/24531"
        },
        {
          "rel": "self-v2",
          "href": "https://api.decidento.com/companies/FR_481741841/v2"
        },
        {
          "rel": "extranet",
          "href": "https://platform.decidento.com/extranet/company/infoplus/24531"
        },
        {
          "rel": "extranet-v2",
          "href": "https://platform.decidento.com/extranet/company/infoplusV2/FR_481741841"
        }
      ],
      "self_link": "https://api.decidento.com/companies/24531",
      "self_v2_link": "https://api.decidento.com/companies/FR_481741841/v2",
      "extranet_link": "https://platform.decidento.com/extranet/company/infoplus/24531",
      "extranet_v2_link": "https://platform.decidento.com/extranet/company/infoplusV2/FR_481741841"
    }
  ],
  "continents": [],
  "countries": [],
  "departments": [
    "Pyrénées Atlantiques"
  ],
  "city_label": "",
  "city_zip_code": "",
  "summary": "Nature: Plan d'investissement sans détail | Stade: En cours | Localisation du signal: Pyrénées Atlantiques",
  "step": "En cours",
  "last_article_link": "https://platform.decidento.com/extranet/article/756220",
  "sectors": null,
  "date_start_invest": null,
  "date_end_invest": null,
  "cout_total_invest": null,
  "nature_invest": [
    "Plan d'investissement sans détail"
  ],
  "step_projet_invest": [
    "En cours"
  ]
}
```

This endpoint retrieves a signal according to ID.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`
 https://api.decidento.com/signals/{signalId}
`

### Query Parameters

Champ       | Type                        | Description                                                              
------------|-----------------------------|--------------------------------------------------------------------------
signalId *        | entier                      | l'id du signal                                                     

### Response

| Champ                                   | Type                        | Description                                                                                      |
|-----------------------------------------|-----------------------------|--------------------------------------------------------------------------------------------------|
| id                                      | Entier                      | Identifiant unique de l'investissement.                                                          |
| departments_list                        | Tableau                     | Liste des départements associés à l'investissement (ex: Pyrénées Atlantiques).                  |
| last_article_pubdate                   | Date                        | Date de publication du dernier article lié à l'investissement (ex: 04/04/2024).                  |
| creation_date                          | Date                        | Date de création de l'enregistrement de l'investissement (ex: 03/04/2024).                       |
| last_update                            | Date                        | Date de la dernière mise à jour de l'enregistrement (ex: 03/04/2024).                            |
| articles                                | Tableau                     | Liste des articles liés à l'investissement.                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;- id           | Entier                      | Identifiant de l'article (ex: 756220).                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;- title        | Chaîne de caractères        | Titre de l'article (ex: Interruption de la production à Mont pour Vertex Bioenergie).            |
| &nbsp;&nbsp;&nbsp;&nbsp;- pub_date     | Date                        | Date de publication de l'article (ex: 04/04/2024).                                             |
| &nbsp;&nbsp;&nbsp;&nbsp;- links        | Tableau                     | Liens associés à l'article (ex: self, extranet).                                               |
| follow_date                            | Date ou null                | Date de suivi de l'investissement, s'il y en a (nullable).                                       |
| type                                   | Chaîne de caractères        | Type d'investissement (ex: K1).                                                                   |
| label_type                             | Chaîne de caractères        | Type d'étiquette de l'investissement (ex: Investissements).                                      |
| status                                 | Chaîne de caractères        | Statut de l'investissement (ex: Détecté).                                                        |
| company_main                           | Objet                       | Informations sur l'entreprise principale associée à l'investissement.                            |
| &nbsp;&nbsp;&nbsp;&nbsp;- id           | Entier                      | Identifiant de l'entreprise (ex: 24531).                                                         |
| &nbsp;&nbsp;&nbsp;&nbsp;- siren        | Chaîne de caractères        | Code SIREN de l'entreprise (ex: 481741841).                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;- siret        | Chaîne de caractères        | Code SIRET de l'entreprise (ex: 48174184100037).                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;- cccid        | Chaîne de caractères        | Code CCCID de l'entreprise (ex: FR_481741841).                                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;- social_name  | Chaîne de caractères        | Raison sociale de l'entreprise (ex: BIOENERGIE DU SUD-OUEST).                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;- siege        | Booléen                     | Indique si c'est le siège de l'entreprise (true/false).                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;- type         | Chaîne de caractères        | Type d'entreprise (ex: main).                                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;- links        | Tableau                     | Liens relatifs à l'entreprise (ex: self, extranet).                                             |
| departments                            | Tableau                     | Liste des départements associés (ex: Pyrénées Atlantiques).                                     |
| city_label                             | Chaîne de caractères        | Libellé de la ville (nullable).                                                                   |
| city_zip_code                          | Chaîne de caractères        | Code postal de la ville (nullable).                                                               |
| summary                                | Chaîne de caractères        | Résumé de l'investissement (ex: Nature: Plan d'investissement sans détail | Stade: En cours).     |
| step                                   | Chaîne de caractères        | Étape actuelle de l'investissement (ex: En cours).                                              |
| last_article_link                      | Chaîne de caractères        | Lien vers le dernier article publié (ex: https://platform.decidento.com/extranet/article/756220). |
| sectors                                | Tableau ou null             | Secteurs d'activité liés à l'investissement (nullable).                                           |
| date_start_invest                      | Date ou null                | Date de début de l'investissement (nullable).                                                    |
| date_end_invest                        | Date ou null                | Date de fin de l'investissement (nullable).                                                      |
| cout_total_invest                      | Entier ou null              | Coût total de l'investissement (nullable).                                                       |
| nature_invest                          | Tableau                     | Nature de l'investissement (ex: Plan d'investissement sans détail).                             |
| step_projet_invest                     | Tableau                     | Étapes du projet d'investissement (ex: En cours).                                              |



## Get a list of signals by IDs

> This query returns JSON structured like this :

This endpoint retrieves a list of signals according to an array of IDs.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`
 https://api.decidento.com/signals/collection/
`

### Query Parameters

Champ       | Type                        | Description                                                              
------------|-----------------------------|--------------------------------------------------------------------------
listIds  *        | entier                      | les IDs des signaux                                                     

### Response

| Champ                                   | Type                        | Description                                                                                      |
|-----------------------------------------|-----------------------------|--------------------------------------------------------------------------------------------------|
| id                                      | Entier                      | Identifiant unique de l'investissement.                                                          |
| departments_list                        | Tableau                     | Liste des départements associés à l'investissement (ex: Pyrénées Atlantiques).                  |
| last_article_pubdate                   | Date                        | Date de publication du dernier article lié à l'investissement (ex: 04/04/2024).                  |
| creation_date                          | Date                        | Date de création de l'enregistrement de l'investissement (ex: 03/04/2024).                       |
| last_update                            | Date                        | Date de la dernière mise à jour de l'enregistrement (ex: 03/04/2024).                            |
| articles                                | Tableau                     | Liste des articles liés à l'investissement.                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;- id           | Entier                      | Identifiant de l'article (ex: 756220).                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;- title        | Chaîne de caractères        | Titre de l'article (ex: Interruption de la production à Mont pour Vertex Bioenergie).            |
| &nbsp;&nbsp;&nbsp;&nbsp;- pub_date     | Date                        | Date de publication de l'article (ex: 04/04/2024).                                             |
| &nbsp;&nbsp;&nbsp;&nbsp;- links        | Tableau                     | Liens associés à l'article (ex: self, extranet).                                               |
| follow_date                            | Date ou null                | Date de suivi de l'investissement, s'il y en a (nullable).                                       |
| type                                   | Chaîne de caractères        | Type d'investissement (ex: K1).                                                                   |
| label_type                             | Chaîne de caractères        | Type d'étiquette de l'investissement (ex: Investissements).                                      |
| status                                 | Chaîne de caractères        | Statut de l'investissement (ex: Détecté).                                                        |
| company_main                           | Objet                       | Informations sur l'entreprise principale associée à l'investissement.                            |
| &nbsp;&nbsp;&nbsp;&nbsp;- id           | Entier                      | Identifiant de l'entreprise (ex: 24531).                                                         |
| &nbsp;&nbsp;&nbsp;&nbsp;- siren        | Chaîne de caractères        | Code SIREN de l'entreprise (ex: 481741841).                                                    |
| &nbsp;&nbsp;&nbsp;&nbsp;- siret        | Chaîne de caractères        | Code SIRET de l'entreprise (ex: 48174184100037).                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;- cccid        | Chaîne de caractères        | Code CCCID de l'entreprise (ex: FR_481741841).                                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;- social_name  | Chaîne de caractères        | Raison sociale de l'entreprise (ex: BIOENERGIE DU SUD-OUEST).                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;- siege        | Booléen                     | Indique si c'est le siège de l'entreprise (true/false).                                        |
| &nbsp;&nbsp;&nbsp;&nbsp;- type         | Chaîne de caractères        | Type d'entreprise (ex: main).                                                                     |
| &nbsp;&nbsp;&nbsp;&nbsp;- links        | Tableau                     | Liens relatifs à l'entreprise (ex: self, extranet).                                             |
| departments                            | Tableau                     | Liste des départements associés (ex: Pyrénées Atlantiques).                                     |
| city_label                             | Chaîne de caractères        | Libellé de la ville (nullable).                                                                   |
| city_zip_code                          | Chaîne de caractères        | Code postal de la ville (nullable).                                                               |
| summary                                | Chaîne de caractères        | Résumé de l'investissement (ex: Nature: Plan d'investissement sans détail | Stade: En cours).     |
| step                                   | Chaîne de caractères        | Étape actuelle de l'investissement (ex: En cours).                                              |
| last_article_link                      | Chaîne de caractères        | Lien vers le dernier article publié (ex: https://platform.decidento.com/extranet/article/756220). |
| sectors                                | Tableau ou null             | Secteurs d'activité liés à l'investissement (nullable).                                           |
| date_start_invest                      | Date ou null                | Date de début de l'investissement (nullable).                                                    |
| date_end_invest                        | Date ou null                | Date de fin de l'investissement (nullable).                                                      |
| cout_total_invest                      | Entier ou null              | Coût total de l'investissement (nullable).                                                       |
| nature_invest                          | Tableau                     | Nature de l'investissement (ex: Plan d'investissement sans détail).                             |
| step_projet_invest                     | Tableau                     | Étapes du projet d'investissement (ex: En cours).                                              |

