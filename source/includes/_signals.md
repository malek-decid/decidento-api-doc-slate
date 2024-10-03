# Signals

L'API "Signals" permet de récupérer des signaux d'activité liés aux sociétés et de consulter des collections de signaux spécifiques. Voici les principales routes :

- **<span class="method-get">GET</span> [/signals](#get-last-signals)** : Récupère les derniers signaux disponibles.
- **<span class="method-get">GET</span> [/signals/{signalId}]()** : Trouve un signal spécifique à partir de son identifiant unique (ID).
- **<span class="method-get">GET</span> [/signals/collection]()** : Récupère une collection de signaux en fournissant une liste d'IDs.

Consultez ce lien pour tester : <a href="https://api.decidento.com/documentation/" target="_blank" rel="noopener noreferrer">API Decidento</a>

## Get last signals

> This query returns JSON structured like this:

```json
{
  "id": 0,
  "last_article_pubdate": "26/03/2021",
  "creation_date": "26/03/2021",
  "last_update": "26/03/2021",
  "follow_date": "26/03/2022",
  "type": "string",
  "label_type": "string",
  "status": "Détecté",
  "company_main": [
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
  ],
  "company_alt": [
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
  ],
  "continents": [
    "string"
  ],
  "countries": [
    "string"
  ],
  "departments": [
    {
      "code": 92,
      "dep": "Hauts de Seine",
      "region": "Île-de-France"
    }
  ],
  "city": [
    {
      "label": "Parcoul-Chenaud",
      "zip_code": "24410",
      "insee_code": "24316",
      "departement_code": "24"
    }
  ],
  "city_label": "string",
  "city_zip_code": "string",
  "surface_totale_facilities": 0,
  "surface_terrain": 0,
  "surface_bati": 0,
  "date_start_facilities": "2024-10-02T14:30:44.398Z",
  "date_end_facilities_building": "2024-10-02T14:30:44.398Z",
  "cout_total_facilities_ground": 0,
  "cout_total_facilities_construction": 0,
  "cout_total_facilities": 0,
  "maitre_ouvrage": {
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
  },
  "maitre_oeuvre": {
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
  },
  "type_projet_facilities": [
    "string"
  ],
  "step_projet_facilities": [
    "string"
  ],
  "building_permit": {
    "permit_number": "08611322A0002",
    "type": "permis_amenager"
  }
}
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

### Response

| Nom                                   | Type                | Description                                                                                     |
|---------------------------------------|---------------------|-------------------------------------------------------------------------------------------------|
| id                                    | Entier              | Identifiant du projet                                                                          |
| last_article_pubdate                  | Chaîne (date)       | Date de publication du dernier article                                                          |
| creation_date                         | Chaîne (date)       | Date de création du projet                                                                      |
| last_update                           | Chaîne (date)       | Date de la dernière mise à jour du projet                                                      |
| follow_date                           | Chaîne (date)       | Date de suivi du projet                                                                          |
| type                                  | Chaîne              | Type du projet                                                                                 |
| label_type                            | Chaîne              | Libellé du type de projet                                                                        |
| status                                | Chaîne              | Statut du projet (ex: "Détecté")                                                               |
| **company_main**                      | Objet               | Informations sur la société principale                                                          |
| &nbsp;&nbsp;&nbsp;company_main.id     | Entier              | Identifiant de la société principale                                                             |
| &nbsp;&nbsp;&nbsp;company_main.siren  | Entier              | SIREN de la société principale                                                                   |
| &nbsp;&nbsp;&nbsp;company_main.siret  | Entier              | SIRET de la société principale                                                                   |
| &nbsp;&nbsp;&nbsp;company_main.siege  | Booléen             | Indique si l'établissement est le siège social                                                  |
| &nbsp;&nbsp;&nbsp;company_main.social_name | Chaîne           | Nom de la société principale                                                                     |
| &nbsp;&nbsp;&nbsp;company_main.sirets | Tableau d'objet     | Liste des SIRET secondaires                                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_main.sirets.siret | Entier  | Numéro SIRET secondaire                                                                         |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_main.sirets.type  | Entier | Type de SIRET                                                                                  |
| &nbsp;&nbsp;&nbsp;company_main.links   | Tableau d'objet     | Liens associés à la société principale                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_main.links.rel     | Chaîne              | Type de lien (ex: "self")                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_main.links.href    | Chaîne              | URL du lien                                                                                     |
| **company_alt**                       | Objet               | Informations sur les sociétés alternatives (similaire à company_main)                          |
| &nbsp;&nbsp;&nbsp;company_alt.id      | Entier              | Identifiant de la société alternative                                                            |
| &nbsp;&nbsp;&nbsp;company_alt.siren   | Entier              | SIREN de la société alternative                                                                  |
| &nbsp;&nbsp;&nbsp;company_alt.siret   | Entier              | SIRET de la société alternative                                                                  |
| &nbsp;&nbsp;&nbsp;company_alt.siege   | Booléen             | Indique si l'établissement est le siège social                                                  |
| &nbsp;&nbsp;&nbsp;company_alt.social_name | Chaîne           | Nom de la société alternative                                                                    |
| &nbsp;&nbsp;&nbsp;company_alt.sirets  | Tableau d'objet     | Liste des SIRET secondaires de la société alternative                                            |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_alt.sirets.siret   | Entier              | Numéro SIRET secondaire                                                                          |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_alt.sirets.type    | Entier              | Type de SIRET                                                                                   |
| &nbsp;&nbsp;&nbsp;company_alt.links    | Tableau d'objet     | Liens associés à la société alternative                                                           |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_alt.links.rel       | Chaîne              | Type de lien (ex: "self")                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;company_alt.links.href      | Chaîne              | URL du lien                                                                                     |
| continents                             | Tableau de chaînes  | Continents associés au projet                                                                    |
| countries                              | Tableau de chaînes  | Pays associés au projet                                                                          |
| **departments**                       | Objet               | Départements associés au projet                                                                  |
| &nbsp;&nbsp;&nbsp;departments.code     | Entier              | Code du département                                                                              |
| &nbsp;&nbsp;&nbsp;departments.dep      | Chaîne              | Nom du département                                                                                |
| &nbsp;&nbsp;&nbsp;departments.region   | Chaîne              | Nom de la région                                                                                 |
| **city**                               | Objet               | Ville associée au projet                                                                         |
| &nbsp;&nbsp;&nbsp;city.label           | Chaîne              | Nom de la ville                                                                                 |
| &nbsp;&nbsp;&nbsp;city.zip_code        | Chaîne              | Code postal de la ville                                                                          |
| &nbsp;&nbsp;&nbsp;city.insee_code      | Chaîne              | Code INSEE de la ville                                                                            |
| &nbsp;&nbsp;&nbsp;city.departement_code | Chaîne              | Code du département                                                                               |
| city_label                             | Chaîne              | Libellé de la ville                                                                               |
| city_zip_code                          | Chaîne              | Code postal de la ville                                                                          |
| surface_totale_facilities              | Entier              | Surface totale des installations                                                                  |
| surface_terrain                        | Entier              | Surface du terrain                                                                                |
| surface_bati                           | Entier              | Surface bâtie                                                                                   |
| date_start_facilities                  | Chaîne (date)       | Date de début des installations                                                                   |
| date_end_facilities_building           | Chaîne (date)       | Date de fin de construction                                                                       |
| cout_total_facilities_ground           | Entier              | Coût total des installations au sol                                                               |
| cout_total_facilities_construction     | Entier              | Coût total des constructions                                                                       |
| cout_total_facilities                  | Entier              | Coût total des installations                                                                      |
| **maitre_ouvrage**                     | Objet               | Informations sur le maître d'ouvrage (similaire à company_main)                                 |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.id    | Entier              | Identifiant du maître d'ouvrage                                                                   |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.siren | Entier              | SIREN du maître d'ouvrage                                                                        |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.siret | Entier              | SIRET du maître d'ouvrage                                                                        |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.siege | Booléen             | Indique si l'établissement est le siège social                                                   |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.social_name | Chaîne         | Nom du maître d'ouvrage                                                                          |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.sirets | Tableau d'objet     | Liste des SIRET du maître d'ouvrage                                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_ouvrage.sirets.siret | Entier | Numéro SIRET                                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_ouvrage.sirets.type  | Entier | Type de SIRET                                                                                   |
| &nbsp;&nbsp;&nbsp;maitre_ouvrage.links | Tableau d'objet     | Liens associés au maître d'ouvrage                                                               |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_ouvrage.links.rel     | Chaîne              | Type de lien (ex: "self")                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_ouvrage.links.href    | Chaîne              | URL du lien                                                                                     |
| **maitre_oeuvre**                      | Objet               | Informations sur le maître d'œuvre (similaire à company_main)                                   |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.id      | Entier              | Identifiant du maître d'œuvre                                                                     |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.siren   | Entier              | SIREN du maître d'œuvre                                                                          |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.siret   | Entier              | SIRET du maître d'œuvre                                                                          |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.siege   | Booléen             | Indique si l'établissement est le siège social                                                   |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.social_name | Chaîne         | Nom du maître d'œuvre                                                                            |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.sirets   | Tableau d'objet     | Liste des SIRET du maître d'œuvre                                                                 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_oeuvre.sirets.siret     | Entier              | Numéro SIRET                                                                                   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_oeuvre.sirets.type      | Entier              | Type de SIRET                                                                                   |
| &nbsp;&nbsp;&nbsp;maitre_oeuvre.links    | Tableau d'objet     | Liens associés au maître d'œuvre                                                                  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_oeuvre.links.rel         | Chaîne              | Type de lien (ex: "self")                                                                       |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;maitre_oeuvre.links.href        | Chaîne              | URL du lien                                                                                     |
| type_projet_facilities                 | Tableau de chaînes  | Type de projet d'installation                                                                    |
| step_projet_facilities                 | Tableau de chaînes  | Étape du projet d'installation                                                                    |
| **building_permit**                    | Objet               | Informations sur le permis de construire                                                         |
| &nbsp;&nbsp;&nbsp;building_permit.permit_number | Chaîne         | Numéro du permis de construire                                                                    |
| &nbsp;&nbsp;&nbsp;building_permit.type   | Chaîne              | Type de permis (ex: "permis_amenager")                                                          |



## Get a signal

> This query returns JSON structured like this :

```json

```

This endpoint retrieves a signal according to ID.
