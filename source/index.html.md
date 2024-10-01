---
title: Decidento API Documentation

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Decidento API
---

# Decidento API documentation

Welcome to the DECIDENTO API ! You can use our API to access Decidento endpoints, which can get information on various Articles, Companies, and Signals in our database.

We have language bindings in Shell, PHP, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with <a href="https://api.decidento.com/" target="_blank" rel="noopener noreferrer">Decidento</a>.

## Path Table

<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>

| Method | Path                                                        | Description                             |
| --- |-------------------------------------------------------------|:----------------------------------------|
| <span class="method-get">GET</span> | [/articles](#get-all-articles)                              | Get last articles                       |
| <span class="method-get">GET</span> | [/articles/search](#search-for-list-of-articles)            | Search for a list of articles           |
| <span class="method-get">GET</span> | [/articles/{articleId}](#find-article-by-id)                | Find article by ID                      |
| <span class="method-get">GET</span> | [/articles/collection](#find-collection-of-articles-by-id)  | Find a collection of articles by IDS    |
| <span class="method-get">GET</span> | [/companies](##get-all-companies)                            | Search companies with parameters        |
| <span class="method-get">GET</span> | [/companies/{companyId}](#getcompaniescompanyid)            | Find company by ID                      |
| <span class="method-get">GET</span> | [/companies/collection](#getcompaniescollection)            | Find a collection of companies by IDS   |
| <span class="method-get">GET</span> | [/companies/v2](#getcompaniesv2)                            | Search companies with parameters        |
| <span class="method-get">GET</span> | [/companies/{companyCccid}/v2](#getcompaniescompanycccidv2) | Find company by CCCID                   |
| <span class="method-get">GET</span> | [/companies/collection/v2](#getcompaniescollectionv2)       | Find a collection of companies by SIREN |
| <span class="method-get">GET</span> | [/signals](#getsignals)                                     | Get last signals                        |
| <span class="method-get">GET</span> | [/signals/{signalId}](#getsignalssignalid)                  | Find signal by ID                       |
| <span class="method-get">GET</span> | [/signals/collection](#getsignalscollection)                | Find collection of signals by IDS       |

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Articles

## Get All Articles

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

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

`GET https://api.decidento.com/articles`

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

Field | Type                                                                                                                         | Description                                                                                                                   
--------- |------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------
id | Entier | index de l'article                                                                                                            
title | Chaine de caractères | Le titre de l'article chez Decidento
text | Chaine de caractères | Le corps de l'article chez Decidento                                                                                          
pub_date | Date (dd/mm/yyyy) | La date de publication de l'article sur Decidento                                                                             
<span class="field">deparments</span> | Tableau[]  | La date de publication de l'article sur Decidento                                                                             
departments.code | Entier | Code officiel du département en France.
departments.dep | Chaine de caractères | Le nom du département.                                                                                                        
departments.region | Chaine de caractères | Le nom de la région à laquelle le département appartient.                                                                     
<span class="field">sources</span> | Tableau[]   | Liste des sources d'information associés à l'article                                                                          
sources.source | Chaine de caractères  | Le nom de la source ou de l'éditeur de l'information. Cela indique d'où provient l'information.                               
sources.pub_date | Date (dd/mm/yyyy) | La date de publication de l'article dans la source de l'information.                                                          
sources.author | Chaine de caractères |  Le nom de l'auteur de l'article ou de la source d'information. Cela indique qui a rédigé ou créé le contenu.
sources.uri | Chaine de caractères | L'URI (Uniform Resource Identifier) ou l'URL de la source. Cela fournit un lien vers l'article ou le contenu source en ligne. 
<span class="field">companies</span> | Tableau[]   | Liste des entreprises associées à l'article.                                                                         
companies.id | Entier   | Identifiant unique de l'entreprise.                                                                                  
companies.siren | Entier   | Le numéro SIREN de l'entreprise. Identifiant unique de 9 chiffres attribué à chaque entreprise en France.              
companies.siret | Entier   | Le numéro SIRET de l'entreprise. Identifiant unique de 14 chiffres qui inclut le SIREN et indique le site de l'entreprise.         
companies.siege | Booléen  | Indique si l'entreprise est le siège social (true) ou non (false).                                                   
companies.social_name | Chaine de caractères | Nom social de l'entreprise. Représente la raison sociale sous laquelle l'entreprise est enregistrée.          
companies.sirets[].siret | Entier | Numéro SIRET associé à l'entreprise (site spécifique).    
companies.sirets[].type | Entier | Type de SIRET (ex : type d'activité).           
companies.links[].rel | Chaine de caractères | Relation du lien (par exemple, `"self"`).   
companies.links[].href | Chaine de caractères | URL du lien.
<span class="field">sectors</span> | Tableau[]   | Liste des secteurs d'activité associés à l'article.                                                                         
sectors[].activity | Chaine de caractères  | Le nom de l'activité ou du secteur dans lequel l'entreprise opère.                               
sectors[].picture | Chaine de caractères | L'URL de l'image représentant le secteur d'activité. 
<span class="field">quoted_articles</span> | Tableau[]   | Liste des articles cités dans l'article principal.                                                                         
quoted_articles[].id | Entier   | Identifiant unique de l'article cité.                                                                                  
quoted_articles[].title | Chaine de caractères | Titre de l'article cité. Représente le sujet principal abordé dans l'article.              
quoted_articles[].links | Objet   | Liens associés à l'article cité. Référence à la structure de liens décrite dans le schéma.                                                                                                                      | If set to false, the result will include kittens that have already been adopted.                                              
<span class="field">signals</span> | Tableau[]   | Liste des signaux associés, contenant des informations sur les entreprises et les projets.   
signals[].id | Entier   | Identifiant unique du signal.                                                                                     
signals[].last_article_pubdate | Date (dd/mm/yyyy) | Date de publication du dernier article associé au signal.                                                       
signals[].creation_date | Date (dd/mm/yyyy) | Date de création du signal.                                                                                      
signals[].last_update | Date (dd/mm/yyyy) | Date de la dernière mise à jour du signal.                                                                      
signals[].follow_date | Date (dd/mm/yyyy) | Date à laquelle le signal a été suivi.                                                                          
signals[].type | Chaine de caractères | Type du signal. Indique la catégorie ou la nature du signal.                                                   
signals[].label_type | Chaine de caractères | Étiquette ou description du type de signal.                                                                     
signals[].status | Chaine de caractères | État actuel du signal, par exemple, "Détecté".                                                                   
signals[].company_main[].id | Entier | Identifiant unique de l'entreprise principale.                                                                    
signals[].company_main[].siren | Entier | Numéro SIREN de l'entreprise principale.                                                                         
signals[].company_main[].siret | Entier | Numéro SIRET de l'entreprise principale.                                                                         
signals[].company_main[].siege | Booléen | Indique si l'entreprise est le siège social.                                                                    
signals[].company_main[].social_name | Chaine de caractères | Nom social de l'entreprise principale.                                                                            
signals[].company_main[].sirets[].siret | Entier | Numéro SIRET associé à l'entreprise.                                                                             
signals[].company_main[].sirets[].type | Entier | Type du SIRET (classification de l'activité).                                                                   
signals[].company_main[].links[].rel | Chaine de caractères | Relation du lien (ex: "self").                                                                                 
signals[].company_main[].links[].href | URI | Lien vers les informations de l'entreprise.                                                                      
signals[].company_alt[].id | Entier | Identifiant unique de l'entreprise alternative.                                                                    
signals[].company_alt[].siren | Entier | Numéro SIREN de l'entreprise alternative.                                                                         
signals[].company_alt[].siret | Entier | Numéro SIRET de l'entreprise alternative.                                                                         
signals[].company_alt[].siege | Booléen | Indique si l'entreprise alternative est le siège social.                                                          
signals[].company_alt[].social_name | Chaine de caractères | Nom social de l'entreprise alternative.                                                                            
signals[].company_alt[].sirets[].siret | Entier | Numéro SIRET associé à l'entreprise alternative.                                                                   
signals[].company_alt[].sirets[].type | Entier | Type du SIRET (classification de l'activité).                                                                   
signals[].company_alt[].links[].rel | Chaine de caractères | Relation du lien (ex: "self").                                                                                 
signals[].company_alt[].links[].href | URI | Lien vers les informations de l'entreprise alternative.                                                           
signals[].continents | Tableau[] | Liste des continents associés au signal.                                                                           
signals[].countries | Tableau[] | Liste des pays associés au signal.                                                                                
signals[].departments[].code | Entier | Code du département associé au signal.                                                                             
signals[].departments[].dep | Chaine de caractères | Nom du département associé au signal.                                                                              
signals[].departments[].region | Chaine de caractères | Nom de la région associée au signal.                                                                              
signals[].city[].label | Chaine de caractères | Nom de la ville associée au signal.                                                                               
signals[].city[].zip_code | Chaine de caractères | Code postal de la ville associée au signal.                                                                       
signals[].city[].insee_code | Chaine de caractères | Code INSEE de la ville associée au signal.                                                                       
signals[].city[].departement_code | Chaine de caractères | Code du département de la ville associée au signal.                                                               
signals[].city_label | Chaine de caractères | Label de la ville associée au signal.                                                                             
signals[].city_zip_code | Chaine de caractères | Code postal de la ville associée au signal (peut être différent de zip_code).                                      
signals[].surface_totale_facilities | Entier | Surface totale des installations associées au signal.                                                             
signals[].surface_terrain | Entier | Surface du terrain associée au signal.                                                                             
signals[].surface_bati | Entier | Surface bâtie associée au signal.                                                                                  
signals[].date_start_facilities | Date (ISO 8601) | Date de début des installations.                                                                                  
signals[].date_end_facilities_building | Date (ISO 8601) | Date de fin de construction des installations.                                                                     
signals[].cout_total_facilities_ground | Entier | Coût total des installations au sol.                                                                              
signals[].cout_total_facilities_construction | Entier | Coût total des constructions des installations.                                                                     
signals[].cout_total_facilities | Entier | Coût total des installations.                                                                                     
signals[].maitre_ouvrage.id | Entier | Identifiant unique du maître d'ouvrage.                                                                            
signals[].maitre_ouvrage.siren | Entier | Numéro SIREN du maître d'ouvrage.                                                                                  
signals[].maitre_ouvrage.siret | Entier | Numéro SIRET du maître d'ouvrage.                                                                                  
signals[].maitre_ouvrage.siege | Booléen | Indique si le maître d'ouvrage est le siège social.                                                               
signals[].maitre_ouvrage.social_name | Chaine de caractères | Nom social du maître d'ouvrage.                                                                                   
signals[].maitre_ouvrage.sirets[].siret | Entier | Numéro SIRET associé au maître d'ouvrage.                                                                         
signals[].maitre_ouvrage.sirets[].type | Entier | Type du SIRET (classification de l'activité) du maître d'ouvrage.                                              
signals[].maitre_ouvrage.links[].rel | Chaine de caractères | Relation du lien (ex: "self") pour le maître d'ouvrage.                                                          
signals[].maitre_ouvrage.links[].href | URI | Lien vers les informations du maître d'ouvrage.                                                                    
signals[].maitre_oeuvre.id | Entier | Identifiant unique du maître d'œuvre.                                                                              
signals[].maitre_oeuvre.siren | Entier | Numéro SIREN du maître d'œuvre.                                                                                  
signals[].maitre_oeuvre.siret | Entier | Numéro SIRET du maître d'œuvre.                                                                                  
signals[].maitre_oeuvre.siege | Booléen | Indique si le maître d'œuvre est le siège social.                                                                 
signals[].maitre_oeuvre.social_name | Chaine de caractères | Nom social du maître d'œuvre.                                                                                    
signals[].maitre_oeuvre.sirets[].siret | Entier | Numéro SIRET associé au maître d'œuvre.                                                                           
signals[].maitre_oeuvre.sirets[].type | Entier | Type du SIRET (classification de l'activité) du maître d'œuvre.                                                  
signals[].maitre_oeuvre.links[].rel | Chaine de caractères | Relation du lien (ex: "self") pour le maître d'œuvre.                                                             
signals[].maitre_oeuvre.links[].href | URI | Lien vers les informations du maître d'œuvre.                                                                      
signals[].type_projet_facilities | Tableau[] | Liste des types de projet associés aux installations.                                                               
signals[].step_projet_facilities | Tableau[] | Liste des étapes de projet associées aux installations.                                                             
signals[].building_permit.permit_number | Chaine de caractères | Numéro du permis de construire associé au signal.                                                                  
signals[].building_permit.type | Chaine de caractères | Type de permis de construire (ex: "permis_amenager").                                                            


[//]: # (<aside class="success">)

[//]: # (Remember — a happy kitten is an authenticated kitten!)

[//]: # (</aside>)

## 	Search for list of articles

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

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

This endpoint retrieves a list of articles.

[//]: # (<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>)

### HTTP Request

`GET https://api.decidento.com/articles/search/`

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
| companies_links              | Tableau[]                     | Liste des liens associés aux entreprises.                                                            |
| companies_links.id           | Entier                        | Identifiant de l'entreprise.                                                                          |
| companies_links.siren        | Entier                        | Numéro SIREN de l'entreprise.                                                                         |
| companies_links.links        | Tableau[]                     | Liste des liens associés à l'entreprise.                                                              |
| companies_links.links.rel     | Chaine de caractères          | Relation du lien (ex. "self").                                                                        |
| companies_links.links.href    | Chaine de caractères          | URI du lien vers l'entreprise.                                                                        |
| links                        | Tableau[]                     | Liste des liens associés à l'article.                                                                 |
| links[].rel                 | Chaine de caractères          | Relation du lien (ex. "self", "extranet").                                                            |
| links[].href                | Chaine de caractères          | URI du lien vers l'article ou l'extranet.                                                            |

## Find Article by id

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like : [this](#get-all-articles)

```json
```

This endpoint retrieves article by id.

### HTTP Request

`GET https://api.decidento.com/articles/{articleId}/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | L'id de l'article voulu

## Find collection of Articles by id

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like : [this](#get-all-articles)

This endpoint retrieves a list of articles by IDs.

### HTTP Request

`GET https://api.decidento.com/articles/collection/`

### Query Parameters

Parameter | Type                            | Description     
--------- |---------------------------------| ----------- 
listIds | Tableau de chaine de caractères | L'id de l'article voulu

# Companies

## Get All Companies

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

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

`GET https://api.decidento.com/companies`

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

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

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

`GET https://api.decidento.com/companies/{companyId}`

### Query Parameters

Field         | Type                 | Description                                     
--------------|----------------------|-------------------------------------------------
companyId *   | Entier ($int64)      | ID of the company to return (ex: 2105)            
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
