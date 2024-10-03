# Articles

L'API "Articles" permet d'interagir avec des articles via différentes requêtes HTTP. Vous pouvez récupérer les derniers articles, effectuer des recherches, ou consulter des collections d'articles à l'aide d'IDs spécifiques. Voici les principales routes :

- **<span class="method-get">GET</span> [/articles](#get-last-articles)** : Récupère les derniers articles disponibles.
- **<span class="method-get">GET</span> [/articles/search](#search-for-list-of-articles)** : Permet de rechercher une liste d'articles en fonction de critères spécifiques.
- **<span class="method-get">GET</span> [/articles/{articleId}](#find-article-by-id)** : Trouve un article précis à partir de son identifiant unique (ID).
- **<span class="method-get">GET</span> [/articles/collection](#find-collection-of-articles-by-id)** : Récupère une collection d'articles en fournissant une liste d'IDs.

Consultez ce lien pour tester : <a href="https://api.decidento.com/documentation/" target="_blank" rel="noopener noreferrer">API Decidento</a>.


## Get last Articles

> This query returns JSON structured like this:

```json
[
  {
    "id": 225741,
    "title": "Partenariat entre Open Tourisme Lab et Altran",
    "text": "Un partenariat entre Open Tourisme Lab Nimes Metropole (<em>siège à Nimes /30 - accélérateur de start-up spécialisées dans le tourisme</em>)&nbsp;et Altran Technologies - Altran (<em>siège à Neuilly-sur-Seine /92 - conseil en innovation et ingénierie avancée - effectif groupe estimé : 12500 - CA légal 2018 : 1 023 212 313€ - CA groupe estimé 2016 : 2 120 000 000€</em>)&nbsp;a été officiellement signé et s'adresse aux professionnels du tourisme. Altran apportera alors son expertise avec des séminaires, des workshops et des audits pour les entreprises accompagnées par Open Tourisme Lab. <a href=\"https://ecomnews.fr/article/Nimes-open-tourisme-tab-renforce-grace-altran-mieux-accompagner-start-up\">Plus d'informations ici</a>.&nbsp;",
    "pub_date": "22/10/2018",
    "departments": [
      {
        "code": 92,
        "dep": "Hauts de Seine",
        "region": "Île-de-France"
      }
    ],
    "sources": [
      {
        "source": "ECOMNEWS",
        "pub_date": "28/01/2020",
        "author": "Denys Bédarride",
        "uri": "https://ecomnews.fr/article/Nimes-open-tourisme-tab-renforce-grace-altran-mieux-accompagner-start-up"
      }
    ],
    "companies": [
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
    "sectors": [
      {
        "activity": "Distribution Spécialisée",
        "picture": "https://api.decidento.com/uploads/medias/Distribution180.png"
      }
    ],
    "quoted_articles": [
      {
        "id": 164243,
        "title": "Une nouvelle chaudière biomasse à 160 M€ pour Norske Skog Golbey ?",
        "links": {
          "$ref": "#/components/schemas/Link/example"
        }
      }
    ],
    "signals": [
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
        "date_start_facilities": "2024-10-01T08:14:43.409Z",
        "date_end_facilities_building": "2024-10-01T08:14:43.409Z",
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
    ]
  }
]
```

This endpoint retrieves a list of articles according to the query parameters shown below.

[//]: # (<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>)

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`
 https://api.decidento.com/articles
`

### Query Parameters

Field         | Type             | Description                                                                        
--------------|------------------|-------------------------------------------------------------------------------------
term          | string (query)    | Search term (keywords, siren, social name, ...)                                     
siren         | integer ($int9)   | Siren of main companies related to article / signals (format: ^([0-9]{9}))          
date_begin    | string (query)    | Begin date published (ex: 2019-03-03)                                               
date_end      | string (query)    | End date published (ex: 2019-03-03)                                                 
limit         | integer (query)   | The maximum records to return. If the value exceeds the maximum (200), the maximum value will be used. Default value: 100
offset        | integer (query)   | Start number for returned articles. Useful for paginate results. Default value: 1    
order         | string (query)    | Order Field. Available values: publishedAt. Default value: publishedAt              
sort          | string (query)    | Sorting direction. Available values: desc, asc. Default value: desc                 
meta          | boolean (query)   | Output paginate info meta. Default value: false                                     
_format       | string (query)    | Output format. Available values: json, xml. Default value: json                     
X-API-VERSION | string (header)   | X-API-VERSION

### Reponse
<style>
  .field {
    font-weight: bold;
  }
</style>

| Nom                                         | Type                                  | Description                                                                                                                      |
|---------------------------------------------|---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| id                                          | Entier                                | Index de l'article                                                                                                             |
| title                                       | Chaîne de caractères                  | Le titre de l'article chez Decidento                                                                                          |
| text                                        | Chaîne de caractères                  | Le corps de l'article chez Decidento                                                                                            |
| pub_date                                    | Date (dd/mm/yyyy)                    | La date de publication de l'article sur Decidento                                                                              |
| **departments**                             | Tableau[]                             | Liste des départements associés à l'article                                                                                     |
| &nbsp;&nbsp;&nbsp;departments.code          | Entier                                | Code officiel du département en France.                                                                                       |
| &nbsp;&nbsp;&nbsp;departments.dep           | Chaîne de caractères                  | Le nom du département.                                                                                                         |
| &nbsp;&nbsp;&nbsp;departments.region        | Chaîne de caractères                  | Le nom de la région à laquelle le département appartient.                                                                      |
| **sources**                                 | Tableau[]                             | Liste des sources d'information associés à l'article                                                                            |
| &nbsp;&nbsp;&nbsp;sources.source             | Chaîne de caractères                  | Le nom de la source ou de l'éditeur de l'information. Cela indique d'où provient l'information.                                 |
| &nbsp;&nbsp;&nbsp;sources.pub_date          | Date (dd/mm/yyyy)                    | La date de publication de l'article dans la source de l'information.                                                           |
| &nbsp;&nbsp;&nbsp;sources.author            | Chaîne de caractères                  | Le nom de l'auteur de l'article ou de la source d'information. Cela indique qui a rédigé ou créé le contenu.                   |
| &nbsp;&nbsp;&nbsp;sources.uri               | Chaîne de caractères                  | L'URI (Uniform Resource Identifier) ou l'URL de la source. Cela fournit un lien vers l'article ou le contenu source en ligne.   |
| **companies**                               | Tableau[]                             | Liste des entreprises associées à l'article.                                                                                   |
| &nbsp;&nbsp;&nbsp;companies.id              | Entier                                | Identifiant unique de l'entreprise.                                                                                             |
| &nbsp;&nbsp;&nbsp;companies.siren           | Entier                                | Le numéro SIREN de l'entreprise. Identifiant unique de 9 chiffres attribué à chaque entreprise en France.                      |
| &nbsp;&nbsp;&nbsp;companies.siret           | Entier                                | Le numéro SIRET de l'entreprise. Identifiant unique de 14 chiffres qui inclut le SIREN et indique le site de l'entreprise.      |
| &nbsp;&nbsp;&nbsp;companies.siege           | Booléen                               | Indique si l'entreprise est le siège social (true) ou non (false).                                                            |
| &nbsp;&nbsp;&nbsp;companies.social_name      | Chaîne de caractères                  | Nom social de l'entreprise. Représente la raison sociale sous laquelle l'entreprise est enregistrée.                             |
| &nbsp;&nbsp;&nbsp;companies.sirets[].siret   | Entier                                | Numéro SIRET associé à l'entreprise (site spécifique).                                                                          |
| &nbsp;&nbsp;&nbsp;companies.sirets[].type    | Entier                                | Type de SIRET (ex : type d'activité).                                                                                          |
| &nbsp;&nbsp;&nbsp;companies.links[].rel       | Chaîne de caractères                  | Relation du lien (par exemple, `"self"`).                                                                                       |
| &nbsp;&nbsp;&nbsp;companies.links[].href      | Chaîne de caractères                  | URL du lien.                                                                                                                  |
| **sectors**                                 | Tableau[]                             | Liste des secteurs d'activité associés à l'article.                                                                            |
| &nbsp;&nbsp;&nbsp;sectors[].activity        | Chaîne de caractères                  | Le nom de l'activité ou du secteur dans lequel l'entreprise opère.                                                              |
| &nbsp;&nbsp;&nbsp;sectors[].picture         | Chaîne de caractères                  | L'URL de l'image représentant le secteur d'activité.                                                                           |
| **quoted_articles**                         | Tableau[]                             | Liste des articles cités dans l'article principal.                                                                              |
| &nbsp;&nbsp;&nbsp;quoted_articles[].id      | Entier                                | Identifiant unique de l'article cité.                                                                                           |
| &nbsp;&nbsp;&nbsp;quoted_articles[].title   | Chaîne de caractères                  | Titre de l'article cité. Représente le sujet principal abordé dans l'article.                                                  |
| &nbsp;&nbsp;&nbsp;quoted_articles[].links    | Objet                                  | Liens associés à l'article cité. Référence à la structure de liens décrite dans le schéma.                                      |
| **signals**                                 | Tableau[]                             | Liste des signaux associés, contenant des informations sur les entreprises et les projets.                                       |
| &nbsp;&nbsp;&nbsp;signals[].id              | Entier                                | Identifiant unique du signal.                                                                                                   |
| &nbsp;&nbsp;&nbsp;signals[].last_article_pubdate | Date (dd/mm/yyyy)                 | Date de publication du dernier article associé au signal.                                                                      |
| &nbsp;&nbsp;&nbsp;signals[].creation_date   | Date (dd/mm/yyyy)                    | Date de création du signal.                                                                                                    |
| &nbsp;&nbsp;&nbsp;signals[].last_update     | Date (dd/mm/yyyy)                    | Date de la dernière mise à jour du signal.                                                                                     |
| &nbsp;&nbsp;&nbsp;signals[].follow_date     | Date (dd/mm/yyyy)                    | Date à laquelle le signal a été suivi.                                                                                         |
| &nbsp;&nbsp;&nbsp;signals[].type            | Chaîne de caractères                  | Type du signal. Indique la catégorie ou la nature du signal.                                                                    |
| &nbsp;&nbsp;&nbsp;signals[].label_type      | Chaîne de caractères                  | Étiquette ou description du type de signal.                                                                                     |
| &nbsp;&nbsp;&nbsp;signals[].status          | Chaîne de caractères                  | État actuel du signal, par exemple, "Détecté".                                                                                  |
| **company_main**                            | Objet                                  | Informations sur l'entreprise principale associée au signal.                                                                    |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].id | Entier                              | Identifiant unique de l'entreprise principale.                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].siren | Entier                             | Numéro SIREN de l'entreprise principale.                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].siret | Entier                             | Numéro SIRET de l'entreprise principale.                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].siege | Booléen                           | Indique si l'entreprise est le siège social.                                                                                   |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].social_name | Chaîne de caractères          | Nom social de l'entreprise principale.                                                                                         |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].sirets[].siret | Entier                       | Numéro SIRET associé à l'entreprise.                                                                                            |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].sirets[].type | Entier                        | Type du SIRET (classification de l'activité).                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].links[].rel | Chaîne de caractères          | Relation du lien (ex: "self").                                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_main[].links[].href | URI                           | Lien vers les informations de l'entreprise.                                                                                   |
| **company_alt**                             | Objet                                  | Informations sur l'entreprise alternative associée au signal.                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].id | Entier                              | Identifiant unique de l'entreprise alternative.                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].siren | Entier                           | Numéro SIREN de l'entreprise alternative.                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].siret | Entier                           | Numéro SIRET de l'entreprise alternative.                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].siege | Booléen                          | Indique si l'entreprise alternative est le siège social.                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].social_name | Chaîne de caractères          | Nom social de l'entreprise alternative.                                                                                         |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].sirets[].siret | Entier                       | Numéro SIRET associé à l'entreprise alternative.                                                                                |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].sirets[].type | Entier                        | Type du SIRET (classification de l'activité).                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].links[].rel | Chaîne de caractères          | Relation du lien (ex: "self").                                                                                                  |
| &nbsp;&nbsp;&nbsp;signals[].company_alt[].links[].href | URI                           | Lien vers les informations de l'entreprise alternative.                                                                         |
| signals[].continents                       | Tableau[]                             | Liste des continents associés au signal.                                                                                        |
| signals[].countries                        | Tableau[]                             | Liste des pays associés au signal.                                                                                             |
| **departments**                            | Objet                                  | Départements associés au signal.                                                                                                 |
| &nbsp;&nbsp;&nbsp;signals[].departments[].code | Entier                            | Code du département associé au signal.                                                                                         |
| &nbsp;&nbsp;&nbsp;signals[].departments[].dep | Chaîne de caractères              | Nom du département associé au signal.                                                                                          |
| &nbsp;&nbsp;&nbsp;signals[].departments[].region | Chaîne de caractères            | Nom de la région associée au signal.                                                                                            |
| **city**                                   | Objet                                  | Ville associée au signal.                                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].city[].label    | Chaîne de caractères                | Nom de la ville associée au signal.                                                                                             |
| &nbsp;&nbsp;&nbsp;signals[].city[].zip_code  | Chaîne de caractères                | Code postal de la ville associée au signal.                                                                                    |
| &nbsp;&nbsp;&nbsp;signals[].city[].insee_code | Chaîne de caractères               | Code INSEE de la ville associée au signal.                                                                                     |
| &nbsp;&nbsp;&nbsp;signals[].city[].departement_code | Chaîne de caractères           | Code du département de la ville associée au signal.                                                                            |
| signals[].city_label                       | Chaîne de caractères                  | Label de la ville associée au signal.                                                                                          |
| signals[].city_zip_code                    | Chaîne de caractères                  | Code postal de la ville associée au signal (peut être différent de zip_code).                                                  |
| signals[].surface_totale_facilities        | Entier                                | Surface totale des installations associées au signal.                                                                          |
| signals[].surface_terrain                  | Entier                                | Surface du terrain associée au signal.                                                                                         |
| signals[].surface_bati                     | Entier                                | Surface bâtie associée au signal.                                                                                              |
| signals[].date_start_facilities            | Date (ISO 8601)                      | Date de début des installations.                                                                                                |
| signals[].date_end_facilities_building     | Date (ISO 8601)                      | Date de fin de construction des installations.                                                                                  |
| signals[].cout_total_facilities_ground      | Entier                                | Coût total des installations au sol.                                                                                            |
| signals[].cout_total_facilities_construction | Entier                               | Coût total des constructions des installations.                                                                                 |
| signals[].cout_total_facilities            | Entier                                | Coût total des installations.                                                                                                   |
| **maitre_ouvrage**                         | Objet                                  | Informations sur le maître d'ouvrage.                                                                                          |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.id | Entier                             | Identifiant unique du maître d'ouvrage.                                                                                        |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.siren | Entier                          | Numéro SIREN du maître d'ouvrage.                                                                                             |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.siret | Entier                          | Numéro SIRET du maître d'ouvrage.                                                                                             |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.siege | Booléen                          | Indique si le maître d'ouvrage est le siège social.                                                                           |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.social_name | Chaîne de caractères         | Nom social du maître d'ouvrage.                                                                                                |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.sirets[].siret | Entier                       | Numéro SIRET associé au maître d'ouvrage.                                                                                     |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.sirets[].type | Entier                        | Type du SIRET (classification de l'activité) du maître d'ouvrage.                                                             |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.links[].rel | Chaîne de caractères         | Relation du lien (ex: "self") pour le maître d'ouvrage.                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].maitre_ouvrage.links[].href | URI                          | Lien vers les informations du maître d'ouvrage.                                                                                |
| **maitre_oeuvre**                          | Objet                                  | Informations sur le maître d'œuvre.                                                                                           |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.id | Entier                             | Identifiant unique du maître d'œuvre.                                                                                         |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.siren | Entier                           | Numéro SIREN du maître d'œuvre.                                                                                               |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.siret | Entier                           | Numéro SIRET du maître d'œuvre.                                                                                               |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.siege | Booléen                          | Indique si le maître d'œuvre est le siège social.                                                                             |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.social_name | Chaîne de caractères          | Nom social du maître d'œuvre.                                                                                                 |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.sirets[].siret | Entier                       | Numéro SIRET associé au maître d'œuvre.                                                                                       |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.sirets[].type | Entier                        | Type du SIRET (classification de l'activité) du maître d'œuvre.                                                               |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.links[].rel | Chaîne de caractères         | Relation du lien (ex: "self") pour le maître d'œuvre.                                                                        |
| &nbsp;&nbsp;&nbsp;signals[].maitre_oeuvre.links[].href | URI                          | Lien vers les informations du maître d'œuvre.                                                                                 |
| signals[].type_projet_facilities           | Tableau[]                             | Liste des types de projet associés aux installations.                                                                          |
| signals[].step_projet_facilities           | Tableau[]                             | Liste des étapes de projet associées aux installations.                                                                        |
| signals[].building_permit.permit_number    | Chaîne de caractères                  | Numéro du permis de construire associé au signal.                                                                               |
| signals[].building_permit.type              | Chaîne de caractères                  | Type de permis de construire (ex: "permis_amenager").                                                                          |



[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## 	Search for list of articles

> This query command returns JSON structured like this:

```json
[
  {
    "id": 225741,
    "pub_date": "22/10/2018",
    "companies_links": [
      {
        "id": 72242,
        "siren": 831946488,
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
    "links": [
      [
        {
          "rel": "self",
          "href": "https://api.decidento.com/articles/2438"
        },
        {
          "rel": "extranet",
          "href": "https://api.decidento.com/extranet/article/24384"
        }
      ]
    ]
  }
]
```

This endpoint retrieves a list of articles according to the query parameters shown below.

[//]: # (<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>)

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/articles/search/`

### Query Parameteres
Field         | Type              | Description                                                                        
--------------|-------------------|-------------------------------------------------------------------------------------
term          | string (query)     | Search term (keywords, siren, social name, ...)                                     
siren         | array ($int9 query)| List of SIREN (comma separated)                                                    
date_begin    | string (query)     | Begin date published (ex: 2019-03-03)                                               
date_end      | string (query)     | End date published (ex: 2019-03-03)                                                 
limit         | integer (query)    | The maximum records to return. If the value exceeds the maximum (200), the maximum value will be used. Default value: 100
offset        | integer (query)    | Start number for returned articles. Useful for paginate results. Default value: 1    
order         | string (query)     | Order Field. Available values: publishedAt. Default value: publishedAt              
sort          | string (query)     | Sorting direction. Available values: desc, asc. Default value: desc                 
meta          | boolean (query)    | Output paginate info meta. Default value: false                                     
_format       | string (query)     | Output format. Available values: json, xml. Default value: json                     
X-API-VERSION | string (header)    | X-API-VERSION

### Reponse

| Field                        | Type                          | Description                                                                                          |
|------------------------------|-------------------------------|------------------------------------------------------------------------------------------------------|
| id                           | Entier                        | Identifiant unique de l'article.                                                                     |
| pub_date                     | Date (dd/mm/yyyy)            | Date de publication de l'article.                                                                    |
| **companies_links**          | Tableau[]                     | Liste des liens associés aux entreprises.                                                            |
| &nbsp;&nbsp;&nbsp;companies_links.id           | Entier                        | Identifiant de l'entreprise.                                                                          |
| &nbsp;&nbsp;&nbsp;companies_links.siren        | Entier                        | Numéro SIREN de l'entreprise.                                                                         |
| &nbsp;&nbsp;&nbsp;companies_links.links        | Tableau[]                     | Liste des liens associés à l'entreprise.                                                              |
| &nbsp;&nbsp;&nbsp;companies_links.links.rel     | Chaîne de caractères          | Relation du lien (ex. "self").                                                                        |
| &nbsp;&nbsp;&nbsp;companies_links.links.href    | Chaîne de caractères          | URI du lien vers l'entreprise.                                                                        |
| **links**                    | Tableau[]                     | Liste des liens associés à l'article.                                                                 |
| &nbsp;&nbsp;&nbsp;links[].rel                 | Chaîne de caractères          | Relation du lien (ex. "self", "extranet").                                                            |
| &nbsp;&nbsp;&nbsp;links[].href                | Chaîne de caractères          | URI du lien vers l'article ou l'extranet.                                                            |

## Find Article by id

> This query returns JSON structured like : [this](#get-all-articles)

```json
```

This endpoint retrieves article by id.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
` https://api.decidento.com/articles/{articleId}/`

### Query Parameters

Parameter | Description
--------- | -----------
ID | L'ID de l'article

## Find collection of Articles by id

> This query returns JSON structured like : [this](#get-all-articles)

This endpoint retrieves a list of articles by IDs.

### HTTP Request
<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>
<span class="method-get">GET </span>
`https://api.decidento.com/articles/collection/`

### Query Parameters

Parameter | Type                            | Description     
--------- |---------------------------------| -------------- 
listIds | Tableau de chaine de caractères | Les IDs des articles
