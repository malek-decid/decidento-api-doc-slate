# Decidento API documentation

> Version 2.0

All endpoints

## Path Table

| Method | Path | Description |
| --- | --- | --- |
| GET | [/articles](#getarticles) | get last articles |
| GET | [/articles/search](#getarticlessearch) | search list of article |
| GET | [/articles/{articleId}](#getarticlesarticleid) | Find article by ID |
| GET | [/articles/collection](#getarticlescollection) | Find a collection of articles by IDS |
| GET | [/companies](#getcompanies) | Search companies with parameters |
| GET | [/companies/{companyId}](#getcompaniescompanyid) | Find company by ID |
| GET | [/companies/collection](#getcompaniescollection) | Find a collection of companies by IDS |
| GET | [/companies/v2](#getcompaniesv2) | Search companies with parameters |
| GET | [/companies/{companyCccid}/v2](#getcompaniescompanycccidv2) | Find company by CCCID |
| GET | [/companies/collection/v2](#getcompaniescollectionv2) | Find a collection of companies by SIREN |
| GET | [/signals](#getsignals) | get last signals |
| GET | [/signals/{signalId}](#getsignalssignalid) | Find signal by ID |
| GET | [/signals/collection](#getsignalscollection) | Find collection of signals by IDS |

## Reference Table

| Name | Path | Description |
| --- | --- | --- |
| X_AUTH_TOKEN | [#/components/securitySchemes/X_AUTH_TOKEN](#componentssecurityschemesx_auth_token) |  |
| X_AUTH_ID | [#/components/securitySchemes/X_AUTH_ID](#componentssecurityschemesx_auth_id) |  |
| SignalLight | [#/components/schemas/SignalLight](#componentsschemassignallight) |  |
| Signal | [#/components/schemas/Signal](#componentsschemassignal) |  |
| Signal_A | [#/components/schemas/Signal_A](#componentsschemassignal_a) |  |
| Signal_B | [#/components/schemas/Signal_B](#componentsschemassignal_b) |  |
| Signal_C | [#/components/schemas/Signal_C](#componentsschemassignal_c) |  |
| Signal_D | [#/components/schemas/Signal_D](#componentsschemassignal_d) |  |
| Signal_E | [#/components/schemas/Signal_E](#componentsschemassignal_e) |  |
| Signal_F | [#/components/schemas/Signal_F](#componentsschemassignal_f) |  |
| Signal_G | [#/components/schemas/Signal_G](#componentsschemassignal_g) |  |
| Signal_H | [#/components/schemas/Signal_H](#componentsschemassignal_h) |  |
| Signal_Hbis | [#/components/schemas/Signal_Hbis](#componentsschemassignal_hbis) |  |
| Signal_I | [#/components/schemas/Signal_I](#componentsschemassignal_i) |  |
| Signal_J | [#/components/schemas/Signal_J](#componentsschemassignal_j) |  |
| Signal_K | [#/components/schemas/Signal_K](#componentsschemassignal_k) |  |
| Signal_K1 | [#/components/schemas/Signal_K1](#componentsschemassignal_k1) |  |
| Signal_L | [#/components/schemas/Signal_L](#componentsschemassignal_l) |  |
| Signal_M | [#/components/schemas/Signal_M](#componentsschemassignal_m) |  |
| Signal_N | [#/components/schemas/Signal_N](#componentsschemassignal_n) |  |
| Signal_O | [#/components/schemas/Signal_O](#componentsschemassignal_o) |  |
| Signal_P | [#/components/schemas/Signal_P](#componentsschemassignal_p) |  |
| Signal_Q | [#/components/schemas/Signal_Q](#componentsschemassignal_q) |  |
| Signal_R | [#/components/schemas/Signal_R](#componentsschemassignal_r) |  |
| Signal_S | [#/components/schemas/Signal_S](#componentsschemassignal_s) |  |
| Signal_T | [#/components/schemas/Signal_T](#componentsschemassignal_t) |  |
| Signal_Tbis | [#/components/schemas/Signal_Tbis](#componentsschemassignal_tbis) |  |
| Signal_U | [#/components/schemas/Signal_U](#componentsschemassignal_u) |  |
| Signal_V | [#/components/schemas/Signal_V](#componentsschemassignal_v) |  |
| Signal_W | [#/components/schemas/Signal_W](#componentsschemassignal_w) |  |
| Signal_X | [#/components/schemas/Signal_X](#componentsschemassignal_x) |  |
| Signal_Y | [#/components/schemas/Signal_Y](#componentsschemassignal_y) |  |
| Signal_Z | [#/components/schemas/Signal_Z](#componentsschemassignal_z) |  |
| Signal_Z1 | [#/components/schemas/Signal_Z1](#componentsschemassignal_z1) |  |
| Signal_Z2 | [#/components/schemas/Signal_Z2](#componentsschemassignal_z2) |  |
| Signal_Z3 | [#/components/schemas/Signal_Z3](#componentsschemassignal_z3) |  |
| Source | [#/components/schemas/Source](#componentsschemassource) |  |
| Link | [#/components/schemas/Link](#componentsschemaslink) |  |
| ArticleLinks | [#/components/schemas/ArticleLinks](#componentsschemasarticlelinks) |  |
| ArticleLink | [#/components/schemas/ArticleLink](#componentsschemasarticlelink) |  |
| Department | [#/components/schemas/Department](#componentsschemasdepartment) |  |
| Sector | [#/components/schemas/Sector](#componentsschemassector) |  |
| QuotedArticle | [#/components/schemas/QuotedArticle](#componentsschemasquotedarticle) |  |
| Article | [#/components/schemas/Article](#componentsschemasarticle) |  |
| CompanyLight | [#/components/schemas/CompanyLight](#componentsschemascompanylight) |  |
| CompanySimple | [#/components/schemas/CompanySimple](#componentsschemascompanysimple) |  |
| Company | [#/components/schemas/Company](#componentsschemascompany) |  |
| Contact | [#/components/schemas/Contact](#componentsschemascontact) |  |
| CompanyLightV2 | [#/components/schemas/CompanyLightV2](#componentsschemascompanylightv2) |  |
| CompanyV2 | [#/components/schemas/CompanyV2](#componentsschemascompanyv2) |  |

## Path Details

***

### [GET]/articles

- Summary  
get last articles

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
term?: string
```

```ts
siren?: integer
```

```ts
date_begin?: string
```

```ts
date_end?: string
```

```ts
limit?: integer //default: 100
```

```ts
offset?: integer //default: 1
```

```ts
order?: enum[publishedAt] //default: publishedAt
```

```ts
sort?: enum[desc, asc] //default: desc
```

```ts
meta?: boolean //default: false
```

```ts
_format?: enum[json, xml] //default: json
```

#### Headers

```ts
X-API-VERSION?: string
```

#### Responses

- 200 successful operation

`application/json`

```ts
{
  id?: integer
  title?: string
  text?: string
  // Format d/m/Y
  pub_date?: string
  departments: {
    code?: string
    dep?: string
    region?: string
  }[]
  sources: {
    source?: string
    // Format d/m/Y
    pub_date?: string
    author?: string
    uri?: string
  }[]
  companies: {
    id?: integer
    siren?: integer
    siret?: integer
    social_name?: string
    siege?: boolean
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
    sirets: {
      siret?: string
      cp?: string
    }[]
  }[]
  sectors: {
    activity?: string
    picture?: string
  }[]
  quoted_articles: {
    id?: integer
    title?: string
    links:#/components/schemas/Link[]
  }[]
  signals?: #/components/schemas/Signal_A | #/components/schemas/Signal_B | #/components/schemas/Signal_C | #/components/schemas/Signal_D | #/components/schemas/Signal_E | #/components/schemas/Signal_F | #/components/schemas/Signal_G | #/components/schemas/Signal_H | #/components/schemas/Signal_Hbis | #/components/schemas/Signal_I | #/components/schemas/Signal_J | #/components/schemas/Signal_K | #/components/schemas/Signal_K1 | #/components/schemas/Signal_L | #/components/schemas/Signal_M | #/components/schemas/Signal_N | #/components/schemas/Signal_O | #/components/schemas/Signal_P | #/components/schemas/Signal_Q | #/components/schemas/Signal_R | #/components/schemas/Signal_S | #/components/schemas/Signal_T | #/components/schemas/Signal_Tbis | #/components/schemas/Signal_U | #/components/schemas/Signal_V | #/components/schemas/Signal_W | #/components/schemas/Signal_X | #/components/schemas/Signal_Y | #/components/schemas/Signal_Z[]
}[]
```

- 400 Bad request

***

### [GET]/articles/search

- Summary  
search list of article

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
term?: string
```

```ts
[]
```

```ts
date_begin?: string
```

```ts
date_end?: string
```

```ts
limit?: integer //default: 100
```

```ts
offset?: integer //default: 1
```

```ts
order?: enum[publishedAt] //default: publishedAt
```

```ts
sort?: enum[desc, asc] //default: desc
```

```ts
meta?: boolean //default: false
```

```ts
_format?: enum[json, xml] //default: json
```

#### Headers

```ts
X-API-VERSION?: string
```

#### Responses

- 200 successful operation

`application/json`

```ts
{
  id?: integer
  // Format d/m/Y
  pub_date?: string
  companies_links: {
    id?: integer
    siren?: integer
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
  }[]
  // #/components/schemas/ArticleLinks
  links: {
    rel?: enum[self, blank, extranet]
    href?: string
  }[][]
}[]
```

- 400 Bad request

***

### [GET]/articles/{articleId}

- Summary  
Find article by ID

- Description  
Returns a single article

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Responses

- 200 successful request

`application/json`

```ts
{
  id?: integer
  title?: string
  text?: string
  // Format d/m/Y
  pub_date?: string
  // Format d/m/Y
  event_date?: string
  author?: string
  nature_info?: enum[International, National]
  departments: {
    code?: string
    dep?: string
    region?: string
  }[]
  country?: string
  sources: {
    source?: string
    // Format d/m/Y
    pub_date?: string
    author?: string
    uri?: string
  }[]
  companies: {
    id?: integer
    siren?: integer
    siret?: integer
    social_name?: string
    siege?: boolean
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
    sirets: {
      siret?: string
      cp?: string
    }[]
  }[]
  sectors: {
    activity?: string
    picture?: string
  }[]
  quoted_articles: {
    id?: integer
    title?: string
    links:#/components/schemas/Link[]
  }[]
  signals?: #/components/schemas/Signal_A | #/components/schemas/Signal_B | #/components/schemas/Signal_C | #/components/schemas/Signal_D | #/components/schemas/Signal_E | #/components/schemas/Signal_F | #/components/schemas/Signal_G | #/components/schemas/Signal_H | #/components/schemas/Signal_Hbis | #/components/schemas/Signal_I | #/components/schemas/Signal_J | #/components/schemas/Signal_K | #/components/schemas/Signal_K1 | #/components/schemas/Signal_L | #/components/schemas/Signal_M | #/components/schemas/Signal_N | #/components/schemas/Signal_O | #/components/schemas/Signal_P | #/components/schemas/Signal_Q | #/components/schemas/Signal_R | #/components/schemas/Signal_S | #/components/schemas/Signal_T | #/components/schemas/Signal_Tbis | #/components/schemas/Signal_U | #/components/schemas/Signal_V | #/components/schemas/Signal_W | #/components/schemas/Signal_X | #/components/schemas/Signal_Y | #/components/schemas/Signal_Z[]
}[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/articles/collection

- Summary  
Find a collection of articles by IDS

- Description  
Returns a collection of articles

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
listIds?: string[]
```

#### Responses

- 200 successful request

`application/json`

```ts
{
  id?: integer
  title?: string
  text?: string
  // Format d/m/Y
  pub_date?: string
  // Format d/m/Y
  event_date?: string
  author?: string
  nature_info?: enum[International, National]
  departments: {
    code?: string
    dep?: string
    region?: string
  }[]
  country?: string
  sources: {
    source?: string
    // Format d/m/Y
    pub_date?: string
    author?: string
    uri?: string
  }[]
  companies: {
    id?: integer
    siren?: integer
    siret?: integer
    social_name?: string
    siege?: boolean
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
    sirets: {
      siret?: string
      cp?: string
    }[]
  }[]
  sectors: {
    activity?: string
    picture?: string
  }[]
  quoted_articles: {
    id?: integer
    title?: string
    links:#/components/schemas/Link[]
  }[]
  signals?: #/components/schemas/Signal_A | #/components/schemas/Signal_B | #/components/schemas/Signal_C | #/components/schemas/Signal_D | #/components/schemas/Signal_E | #/components/schemas/Signal_F | #/components/schemas/Signal_G | #/components/schemas/Signal_H | #/components/schemas/Signal_Hbis | #/components/schemas/Signal_I | #/components/schemas/Signal_J | #/components/schemas/Signal_K | #/components/schemas/Signal_K1 | #/components/schemas/Signal_L | #/components/schemas/Signal_M | #/components/schemas/Signal_N | #/components/schemas/Signal_O | #/components/schemas/Signal_P | #/components/schemas/Signal_Q | #/components/schemas/Signal_R | #/components/schemas/Signal_S | #/components/schemas/Signal_T | #/components/schemas/Signal_Tbis | #/components/schemas/Signal_U | #/components/schemas/Signal_V | #/components/schemas/Signal_W | #/components/schemas/Signal_X | #/components/schemas/Signal_Y | #/components/schemas/Signal_Z[]
}[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/companies

- Summary  
Search companies with parameters

- Description  
Returns a list of companies

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
siren?: integer
```

```ts
term?: string
```

```ts
limit?: integer //default: 100
```

```ts
offset?: integer //default: 1
```

```ts
order?: enum[socialName, siren, updatedAt] //default: socialName
```

```ts
sort?: enum[desc, asc] //default: desc
```

```ts
meta?: boolean
```

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful request

`application/json`

```ts
{
  id?: integer
  siren?: integer
  siret?: integer
  social_name?: string
  siege?: boolean
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
  sirets: {
    siret?: string
    cp?: string
  }[]
}[]
```

- 400 Bad request

***

### [GET]/companies/{companyId}

- Summary  
Find company by ID

- Description  
Returns a single company

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful request

`application/json`

```ts
undefined?: #/components/schemas/CompanyLight & {
   last_modified?: string
   enseigne?: string
   sigle?: string
   rcs?: string
   tva_number?: string
   index_euro?: integer
   // Format d/m/Y
   immatriculation_date?: string
   naf_code?: string
   juridic_form?: string
   type_etablissement?: enum[0, 1, 2]
   categorie_full?: string
   categorie_light?: string
   capital_social?: integer
   fonds_propres?: integer
   ca_bilan?: integer
   effectif_precis?: integer
   resultat_net?: integer
   resultat_exploitation?: integer
   // Format d/m/Y
   date_cloture?: string
   radiate?: boolean
   indice_risque_info_legal?: string
   // Score between 0-10
   indice_risque_score3?: string
   anne_indice_risque_score3?: string
   nb_actionnaires?: integer
   nb_filliales_directes?: integer
   nb_filliales_indirectes?: integer
   address?: string
   zip?: string
   city?: string
   department?: string
   country?: string
   geo_lat?: number
   geo_long?: number
   telephone_number?: string
   fax_number?: string
   web_site?: string
   url_maps?: string
   url_viadeo"?: string
   url_twitter"?: string
   url_gnews"?: string
   url_wikipedia"?: string
   url_facebook"?: string
   url_linkedin"?: string
   url_score3"?: string
   url_scoopit"?: string
   logo_url"?: string
   email_contact"?: string
   contacts: {
     name?: string
     role?: string
   }[]
   nb_actes?: integer
 }[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/companies/collection

- Summary  
Find a collection of companies by IDS

- Description  
Returns a collection of companies

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
listIds?: string[]
```

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful request

`application/json`

```ts
undefined?: #/components/schemas/CompanyLight & {
   last_modified?: string
   enseigne?: string
   sigle?: string
   rcs?: string
   tva_number?: string
   index_euro?: integer
   // Format d/m/Y
   immatriculation_date?: string
   naf_code?: string
   juridic_form?: string
   type_etablissement?: enum[0, 1, 2]
   categorie_full?: string
   categorie_light?: string
   capital_social?: integer
   fonds_propres?: integer
   ca_bilan?: integer
   effectif_precis?: integer
   resultat_net?: integer
   resultat_exploitation?: integer
   // Format d/m/Y
   date_cloture?: string
   radiate?: boolean
   indice_risque_info_legal?: string
   // Score between 0-10
   indice_risque_score3?: string
   anne_indice_risque_score3?: string
   nb_actionnaires?: integer
   nb_filliales_directes?: integer
   nb_filliales_indirectes?: integer
   address?: string
   zip?: string
   city?: string
   department?: string
   country?: string
   geo_lat?: number
   geo_long?: number
   telephone_number?: string
   fax_number?: string
   web_site?: string
   url_maps?: string
   url_viadeo"?: string
   url_twitter"?: string
   url_gnews"?: string
   url_wikipedia"?: string
   url_facebook"?: string
   url_linkedin"?: string
   url_score3"?: string
   url_scoopit"?: string
   logo_url"?: string
   email_contact"?: string
   contacts: {
     name?: string
     role?: string
   }[]
   nb_actes?: integer
 }[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/companies/v2

- Summary  
Search companies with parameters

- Description  
Returns a list of companies

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
siren?: integer
```

```ts
siret?: integer
```

```ts
term?: string
```

```ts
code_postal?: string
```

```ts
ville?: string
```

```ts
pays?: string
```

```ts
naf?: string
```

```ts
radiee?: integer
```

```ts
appartient_groupe?: integer
```

```ts
derniere_maj?: string
```

```ts
limit?: integer //default: 100
```

```ts
offset?: integer //default: 1
```

```ts
order?: enum[raison_sociale_keyword, last_kpi.ca_bilan, last_kpi.effectif, cccid, last_modified] //default: last_modified
```

```ts
sort?: enum[desc, asc] //default: desc
```

```ts
meta?: boolean
```

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful request

`application/json`

```ts
{
  cccid?: string
  siren?: integer
  siret_siege?: integer
  raison_sociale?: string
  type_etablissement?: string
  appartient_groupe?: boolean
  adresse_complete?: string
  adresse_postale?: string
  code_postal?: string
  ville?: string
  last_modified?: string
  sigle?: string
  resume_activite?: string
  pays?: string
  radiee?: boolean
  nbre_signaux?: integer
  nbre_articles?: integer
  logo_url?: string
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
}[]
```

- 400 Bad request

***

### [GET]/companies/{companyCccid}/v2

- Summary  
Find company by CCCID

- Description  
Returns a single company

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful request

`application/json`

```ts
undefined?: #/components/schemas/CompanyLightV2 & {
   nombre_etablissements_secondaires_inactifs?: integer
   nombre_etablissements_secondaires_actifs?: integer
   caractere_employeur?: boolean
   enseignes?: string
   date_creation?: string
   numero_tva?: string
   telephone?: string
   departement_label?: string
   departement?: string
   geo_lat?: string
   geo_long?: string
   secteur_activité_lies?: string[]
   code_ape_lies: {
     code_ape?: string
     code_ape_label?: string
   }[]
   code_ape?: string
   code_ape_brut?: string
   code_ape_label?: string
   code_ape_complet?: string
   forme_juridique_code?: string
   forme_juridique?: string
   type_entreprise?: string
   site_ecommerce?: boolean
   activite_rd?: boolean
   activite_export?: boolean
   cac40?: boolean
   startup?: boolean
   secteur_industriel?: boolean
   entreprise_fintech?: boolean
   entreprise_familiale?: boolean
   entreprise_b2c?: boolean
   entreprise_b2b?: boolean
   entreprise_biotech_medtech?: boolean
   website?: string
   url_twitter?: string
   url_facebook?: string
   url_linkedin?: string
   email_contact?: string
   code_confidentialite?: boolean
   avertissement_bilan?: string
   subventions_investissements?: integer
   participation_bilan?: integer
   resultat_bilan?: integer
   resultat_net_consolide?: integer
   dotations_amortissements?: integer
   ca_consolide?: integer
   resultat_exploitation?: integer
   ca_bilan?: integer
   impots_taxes?: integer
   effectif_sous_traitance?: integer
   charges_financieres?: integer
   salaires_traitements?: integer
   ca_export?: integer
   ca_france?: integer
   effectif?: integer
   fonds_propres?: integer
   capital_social?: integer
   duree_exercice?: integer
   annee_cloture_exercice?: string
   date_cloture_exercice?: string
   contacts: {
     type?: string
     name?: string
     first_name?: string
     role?: string
   }[]
 }[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/companies/collection/v2

- Summary  
Find a collection of companies by SIREN

- Description  
Returns a collection of companies

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
listIds?: integer[]
```

#### Responses

- 200 successful request

`application/json`

```ts
undefined?: #/components/schemas/CompanyLightV2 & {
   nombre_etablissements_secondaires_inactifs?: integer
   nombre_etablissements_secondaires_actifs?: integer
   caractere_employeur?: boolean
   enseignes?: string
   date_creation?: string
   numero_tva?: string
   telephone?: string
   departement_label?: string
   departement?: string
   geo_lat?: string
   geo_long?: string
   secteur_activité_lies?: string[]
   code_ape_lies: {
     code_ape?: string
     code_ape_label?: string
   }[]
   code_ape?: string
   code_ape_brut?: string
   code_ape_label?: string
   code_ape_complet?: string
   forme_juridique_code?: string
   forme_juridique?: string
   type_entreprise?: string
   site_ecommerce?: boolean
   activite_rd?: boolean
   activite_export?: boolean
   cac40?: boolean
   startup?: boolean
   secteur_industriel?: boolean
   entreprise_fintech?: boolean
   entreprise_familiale?: boolean
   entreprise_b2c?: boolean
   entreprise_b2b?: boolean
   entreprise_biotech_medtech?: boolean
   website?: string
   url_twitter?: string
   url_facebook?: string
   url_linkedin?: string
   email_contact?: string
   code_confidentialite?: boolean
   avertissement_bilan?: string
   subventions_investissements?: integer
   participation_bilan?: integer
   resultat_bilan?: integer
   resultat_net_consolide?: integer
   dotations_amortissements?: integer
   ca_consolide?: integer
   resultat_exploitation?: integer
   ca_bilan?: integer
   impots_taxes?: integer
   effectif_sous_traitance?: integer
   charges_financieres?: integer
   salaires_traitements?: integer
   ca_export?: integer
   ca_france?: integer
   effectif?: integer
   fonds_propres?: integer
   capital_social?: integer
   duree_exercice?: integer
   annee_cloture_exercice?: string
   date_cloture_exercice?: string
   contacts: {
     type?: string
     name?: string
     first_name?: string
     role?: string
   }[]
 }[]
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/signals

- Summary  
get last signals

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
limit?: integer //default: 200
```

```ts
offset?: integer //default: 1
```

```ts
order?: enum[updatedAt, publishedAt] //default: updatedAt
```

```ts
sort?: enum[desc, asc] //default: desc
```

```ts
meta?: boolean
```

```ts
_format?: enum[json, xml] //default: json
```

#### Responses

- 200 successful operation

`application/json`

```ts
{
  id?: integer
  type: {
    id?: integer
    code?: string
    label?: string
  }[]
  // Signal Status
  status?: enum[Détecté, Suivi, Terminé]
  links: {
    rel?: string
    href?: string
  }[]
  departments_list: {
    code?: string
    dep?: string
    region?: string
  }[]
  // Date de publication du dernier article (dd/mm/YYYY)
  last_article_pubdate?: string
  // Date de création du signal (dd/mm/YYYY)
  creation_date?: string
  // Date de mise à jour du signal (dd/mm/YYYY)
  last_update?: string
}[]
```

- 400 Bad request

***

### [GET]/signals/{signalId}

- Summary  
Find signal by ID

- Description  
Returns a single signal

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Responses

- 200 successful operation

`application/json`

```ts
{
  "oneOf": [
    {
      "$ref": "#/components/schemas/Signal_A"
    },
    {
      "$ref": "#/components/schemas/Signal_B"
    },
    {
      "$ref": "#/components/schemas/Signal_C"
    },
    {
      "$ref": "#/components/schemas/Signal_D"
    },
    {
      "$ref": "#/components/schemas/Signal_E"
    },
    {
      "$ref": "#/components/schemas/Signal_F"
    },
    {
      "$ref": "#/components/schemas/Signal_G"
    },
    {
      "$ref": "#/components/schemas/Signal_H"
    },
    {
      "$ref": "#/components/schemas/Signal_Hbis"
    },
    {
      "$ref": "#/components/schemas/Signal_I"
    },
    {
      "$ref": "#/components/schemas/Signal_J"
    },
    {
      "$ref": "#/components/schemas/Signal_K"
    },
    {
      "$ref": "#/components/schemas/Signal_K1"
    },
    {
      "$ref": "#/components/schemas/Signal_L"
    },
    {
      "$ref": "#/components/schemas/Signal_M"
    },
    {
      "$ref": "#/components/schemas/Signal_N"
    },
    {
      "$ref": "#/components/schemas/Signal_O"
    },
    {
      "$ref": "#/components/schemas/Signal_P"
    },
    {
      "$ref": "#/components/schemas/Signal_Q"
    },
    {
      "$ref": "#/components/schemas/Signal_R"
    },
    {
      "$ref": "#/components/schemas/Signal_S"
    },
    {
      "$ref": "#/components/schemas/Signal_T"
    },
    {
      "$ref": "#/components/schemas/Signal_Tbis"
    },
    {
      "$ref": "#/components/schemas/Signal_U"
    },
    {
      "$ref": "#/components/schemas/Signal_V"
    },
    {
      "$ref": "#/components/schemas/Signal_W"
    },
    {
      "$ref": "#/components/schemas/Signal_X"
    },
    {
      "$ref": "#/components/schemas/Signal_Y"
    },
    {
      "$ref": "#/components/schemas/Signal_Z"
    },
    {
      "$ref": "#/components/schemas/Signal_Z1"
    },
    {
      "$ref": "#/components/schemas/Signal_Z2"
    },
    {
      "$ref": "#/components/schemas/Signal_Z3"
    }
  ]
}
```

- 400 Bad request

- 404 Invalid ID supplied

***

### [GET]/signals/collection

- Summary  
Find collection of signals by IDS

- Description  
Returns a colelction of signals

- Security  
X_AUTH_TOKEN  
X_AUTH_ID  

#### Parameters(Query)

```ts
listIds?: integer[]
```

#### Responses

- 200 successful operation

`application/json`

```ts
{
  "oneOf": [
    {
      "$ref": "#/components/schemas/Signal_A"
    },
    {
      "$ref": "#/components/schemas/Signal_B"
    },
    {
      "$ref": "#/components/schemas/Signal_C"
    },
    {
      "$ref": "#/components/schemas/Signal_D"
    },
    {
      "$ref": "#/components/schemas/Signal_E"
    },
    {
      "$ref": "#/components/schemas/Signal_F"
    },
    {
      "$ref": "#/components/schemas/Signal_G"
    },
    {
      "$ref": "#/components/schemas/Signal_H"
    },
    {
      "$ref": "#/components/schemas/Signal_Hbis"
    },
    {
      "$ref": "#/components/schemas/Signal_I"
    },
    {
      "$ref": "#/components/schemas/Signal_J"
    },
    {
      "$ref": "#/components/schemas/Signal_K"
    },
    {
      "$ref": "#/components/schemas/Signal_K1"
    },
    {
      "$ref": "#/components/schemas/Signal_L"
    },
    {
      "$ref": "#/components/schemas/Signal_M"
    },
    {
      "$ref": "#/components/schemas/Signal_N"
    },
    {
      "$ref": "#/components/schemas/Signal_O"
    },
    {
      "$ref": "#/components/schemas/Signal_P"
    },
    {
      "$ref": "#/components/schemas/Signal_Q"
    },
    {
      "$ref": "#/components/schemas/Signal_R"
    },
    {
      "$ref": "#/components/schemas/Signal_S"
    },
    {
      "$ref": "#/components/schemas/Signal_T"
    },
    {
      "$ref": "#/components/schemas/Signal_Tbis"
    },
    {
      "$ref": "#/components/schemas/Signal_U"
    },
    {
      "$ref": "#/components/schemas/Signal_V"
    },
    {
      "$ref": "#/components/schemas/Signal_W"
    },
    {
      "$ref": "#/components/schemas/Signal_X"
    },
    {
      "$ref": "#/components/schemas/Signal_Y"
    },
    {
      "$ref": "#/components/schemas/Signal_Z"
    },
    {
      "$ref": "#/components/schemas/Signal_Z1"
    },
    {
      "$ref": "#/components/schemas/Signal_Z2"
    },
    {
      "$ref": "#/components/schemas/Signal_Z3"
    }
  ]
}
```

- 400 Bad request

- 404 Invalid ID supplied

## References

### #/components/securitySchemes/X_AUTH_TOKEN

```ts
{
  "type": "apiKey",
  "in": "header",
  "name": "X-AUTH-TOKEN"
}
```

### #/components/securitySchemes/X_AUTH_ID

```ts
{
  "type": "apiKey",
  "in": "header",
  "name": "X-AUTH-ID"
}
```

### #/components/schemas/SignalLight

```ts
{
  id?: integer
  type: {
    id?: integer
    code?: string
    label?: string
  }[]
  // Signal Status
  status?: enum[Détecté, Suivi, Terminé]
  links: {
    rel?: string
    href?: string
  }[]
  departments_list: {
    code?: string
    dep?: string
    region?: string
  }[]
  // Date de publication du dernier article (dd/mm/YYYY)
  last_article_pubdate?: string
  // Date de création du signal (dd/mm/YYYY)
  creation_date?: string
  // Date de mise à jour du signal (dd/mm/YYYY)
  last_update?: string
}
```

### #/components/schemas/Signal

```ts
{
  id?: integer
  // Date de publication du dernier article (dd/mm/YYYY)
  last_article_pubdate?: string
  // Date de création du signal (dd/mm/YYYY)
  creation_date?: string
  // Date de mise à jour du signal (dd/mm/YYYY)
  last_update?: string
  // Date de mise à jour du statut suivi du signal (dd/mm/YYYY)
  follow_date?: string
  type: string
  label_type?: string
  // Order Status
  status?: enum[Détecté, Suivi, Terminé]
  company_main: {
    id?: integer
    siren?: integer
    siret?: integer
    social_name?: string
    siege?: boolean
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
    sirets: {
      siret?: string
      cp?: string
    }[]
  }[]
  company_alt:#/components/schemas/CompanyLight[]
  continents?: string[]
  countries?: string[]
  departments: {
    code?: string
    dep?: string
    region?: string
  }[]
  city: {
    label?: string
    zip_code?: string
    insee_code?: string
    departement_code?: string
  }[]
  city_label?: string
  city_zip_code?: string
}
```

### #/components/schemas/Signal_A

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "surface_totale_facilities": {
          "type": "integer"
        },
        "surface_terrain": {
          "type": "integer"
        },
        "surface_bati": {
          "type": "integer"
        },
        "date_start_facilities": {
          "type": "string",
          "format": "date-time"
        },
        "date_end_facilities_building": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_facilities_ground": {
          "type": "integer"
        },
        "cout_total_facilities_construction": {
          "type": "integer"
        },
        "cout_total_facilities": {
          "type": "integer"
        },
        "maitre_ouvrage": {
          "$ref": "#/components/schemas/CompanyLight"
        },
        "maitre_oeuvre": {
          "$ref": "#/components/schemas/CompanyLight"
        },
        "type_projet_facilities": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_facilities": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "building_permit": {
          "type": "object",
          "properties": {
            "permit_number": {
              "type": "string"
            },
            "type": {
              "type": "string"
            }
          },
          "example": {
            "permit_number": "08611322A0002",
            "type": "permis_amenager"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_B

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "surface_totale_construction": {
          "type": "integer"
        },
        "surface_totale_construction_ground": {
          "type": "integer"
        },
        "date_start_construction": {
          "type": "string",
          "format": "date-time"
        },
        "date_end_construction": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_construction": {
          "type": "integer"
        },
        "cout_total_facilities_construction": {
          "type": "integer"
        },
        "cout_total_facilities": {
          "type": "integer"
        },
        "maitre_ouvrage": {
          "$ref": "#/components/schemas/CompanyLight"
        },
        "nature_op_construction_detail": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "nature_op_construction": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_construction": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "linked_projet_construction": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "building_permit": {
          "type": "object",
          "properties": {
            "permit_number": {
              "type": "string"
            },
            "type": {
              "type": "string"
            }
          },
          "example": {
            "permit_number": "02431621R0016",
            "type": "pc_dp_creant_logements"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_C

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_infrastructures_works": {
          "type": "string",
          "format": "date-time"
        },
        "date_end_infrastructures_works": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_infrastructures": {
          "type": "integer"
        },
        "maitre_ouvrage": {
          "$ref": "#/components/schemas/CompanyLight"
        },
        "type_projet_infrastructures": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_infrastructures": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_D

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "type_projet_disputes": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_disputes": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_E

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_infrastructures_implantation": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_creation_invest": {
          "type": "integer"
        },
        "etablishement_number_creation": {
          "type": "integer"
        },
        "type_projet_creation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_creation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_F

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_op_growth": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_growth": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_G

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_relocation": {
          "type": "string",
          "format": "date-time"
        },
        "nature_op_relocation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "type_projet_relocation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_relocation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_H

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_op_export": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_export": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Hbis

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_op_export_goods": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_export_goods": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_I

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_end_closing": {
          "type": "string",
          "format": "date-time"
        },
        "nature_op_export": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_export": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_J

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_end_closing": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_innovation": {
          "type": "integer"
        },
        "step_projet_innovation": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_K

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_invest_materials": {
          "type": "string",
          "format": "date-time"
        },
        "date_end_invest_materials": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_invest_materials": {
          "type": "integer"
        },
        "step_projet_invest_materials": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_K1

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_invest": {
          "type": "string",
          "format": "date-time"
        },
        "date_end_invest": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_invest": {
          "type": "integer"
        },
        "step_projet_invest": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "nature_invest": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_L

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "cout_total_fundraising": {
          "type": "integer"
        },
        "nature_op_fundraising": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "type_projet_operation_fundraising": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_fundraising": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "linked_projet_fundraising": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_M

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "effectif_dismissals": {
          "type": "integer"
        },
        "type_projet_dismissals": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_dismissals": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_N

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "effectif_recruitments": {
          "type": "integer"
        },
        "type_projet_recruitments_functions": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_recruitments": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_O

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_receivership": {
          "type": "string",
          "format": "date-time"
        },
        "type_projet_receivership": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_receivership": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_P

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "cout_total_transaction_fusacq": {
          "type": "integer"
        },
        "type_projet_fusacq": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_fusacq": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Q

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "cout_total_public_financing": {
          "type": "integer"
        },
        "type_projet_public_financing": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_public_financing": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_R

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "type_projet_decline": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_S

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_launch": {
          "type": "string",
          "format": "date-time"
        },
        "type_projet_launch": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_launch": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_T

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_invest_rd": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_invest_rd": {
          "type": "integer"
        },
        "step_projet_rd": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Tbis

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_invest": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_invest": {
          "type": "integer"
        },
        "step_projet": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_U

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_nomination": {
          "type": "string",
          "format": "date-time"
        },
        "identity_nomination": {
          "type": "string"
        },
        "type_projet_nomination_function": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_nomination": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_V

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_start_invest_communication": {
          "type": "string",
          "format": "date-time"
        },
        "cout_total_invest_communication": {
          "type": "integer"
        },
        "nature_investment": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_invest_communication": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_W

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "surface_totale_land_frame": {
          "type": "integer"
        },
        "cout_total_land_frame_ope": {
          "type": "integer"
        },
        "cout_total_land_frame_sale": {
          "type": "integer"
        },
        "type_projet_land_frame": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_land_frame": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_X

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object"
    }
  ]
}
```

### #/components/schemas/Signal_Y

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "type_projet_information": {
          "type": "array",
          "items": {
            "type": "string"
          }
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Z

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "date_event": {
          "type": "string",
          "format": "date-time"
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Z1

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_rse": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_rse": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "cout_total_invest_rse": {
          "type": "integer"
        },
        "estimated_date": {
          "type": "string",
          "format": "date-time"
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Z2

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_restructuring": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_restructuring": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "nb_restructuring": {
          "type": "integer"
        },
        "cout_total_invest": {
          "type": "integer"
        },
        "estimated_date": {
          "type": "string",
          "format": "date-time"
        }
      }
    }
  ]
}
```

### #/components/schemas/Signal_Z3

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/Signal"
    },
    {
      "type": "object",
      "properties": {
        "nature_act": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "step_projet_act": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "type_act": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "decision": {
          "type": "string"
        },
        "operation_detail": {
          "type": "integer"
        },
        "act_id": {
          "type": "string"
        },
        "estimated_date": {
          "type": "string",
          "format": "date-time"
        }
      }
    }
  ]
}
```

### #/components/schemas/Source

```ts
{
  source?: string
  // Format d/m/Y
  pub_date?: string
  author?: string
  uri?: string
}
```

### #/components/schemas/Link

```ts
{
  rel?: enum[self, blank]
  href?: string
}
```

### #/components/schemas/ArticleLinks

```ts
{
  rel?: enum[self, blank, extranet]
  href?: string
}[]
```

### #/components/schemas/ArticleLink

```ts
{
  rel?: enum[self, blank, extranet]
  href?: string
}
```

### #/components/schemas/Department

```ts
{
  code?: string
  dep?: string
  region?: string
}
```

### #/components/schemas/Sector

```ts
{
  activity?: string
  picture?: string
}
```

### #/components/schemas/QuotedArticle

```ts
{
  id?: integer
  title?: string
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
}
```

### #/components/schemas/Article

```ts
{
  id?: integer
  title?: string
  text?: string
  // Format d/m/Y
  pub_date?: string
  // Format d/m/Y
  event_date?: string
  author?: string
  nature_info?: enum[International, National]
  departments: {
    code?: string
    dep?: string
    region?: string
  }[]
  country?: string
  sources: {
    source?: string
    // Format d/m/Y
    pub_date?: string
    author?: string
    uri?: string
  }[]
  companies: {
    id?: integer
    siren?: integer
    siret?: integer
    social_name?: string
    siege?: boolean
    links: {
      rel?: enum[self, blank]
      href?: string
    }[]
    sirets: {
      siret?: string
      cp?: string
    }[]
  }[]
  sectors: {
    activity?: string
    picture?: string
  }[]
  quoted_articles: {
    id?: integer
    title?: string
    links:#/components/schemas/Link[]
  }[]
  signals?: #/components/schemas/Signal_A | #/components/schemas/Signal_B | #/components/schemas/Signal_C | #/components/schemas/Signal_D | #/components/schemas/Signal_E | #/components/schemas/Signal_F | #/components/schemas/Signal_G | #/components/schemas/Signal_H | #/components/schemas/Signal_Hbis | #/components/schemas/Signal_I | #/components/schemas/Signal_J | #/components/schemas/Signal_K | #/components/schemas/Signal_K1 | #/components/schemas/Signal_L | #/components/schemas/Signal_M | #/components/schemas/Signal_N | #/components/schemas/Signal_O | #/components/schemas/Signal_P | #/components/schemas/Signal_Q | #/components/schemas/Signal_R | #/components/schemas/Signal_S | #/components/schemas/Signal_T | #/components/schemas/Signal_Tbis | #/components/schemas/Signal_U | #/components/schemas/Signal_V | #/components/schemas/Signal_W | #/components/schemas/Signal_X | #/components/schemas/Signal_Y | #/components/schemas/Signal_Z[]
}
```

### #/components/schemas/CompanyLight

```ts
{
  id?: integer
  siren?: integer
  siret?: integer
  social_name?: string
  siege?: boolean
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
  sirets: {
    siret?: string
    cp?: string
  }[]
}
```

### #/components/schemas/CompanySimple

```ts
{
  id?: integer
  siren?: integer
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
}
```

### #/components/schemas/Company

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/CompanyLight"
    },
    {
      "type": "object",
      "properties": {
        "last_modified": {
          "type": "string",
          "format": "date-time"
        },
        "enseigne": {
          "type": "string"
        },
        "sigle": {
          "type": "string"
        },
        "rcs": {
          "type": "string"
        },
        "tva_number": {
          "type": "string"
        },
        "index_euro": {
          "type": "integer"
        },
        "immatriculation_date": {
          "type": "string",
          "format": "date",
          "pattern": "^\\d{2}/\\d{2}/\\d{4}$",
          "description": "Format d/m/Y"
        },
        "naf_code": {
          "type": "string"
        },
        "juridic_form": {
          "type": "string"
        },
        "type_etablissement": {
          "type": "string",
          "enum": [
            "0",
            "1",
            "2"
          ]
        },
        "categorie_full": {
          "type": "string"
        },
        "categorie_light": {
          "type": "string"
        },
        "capital_social": {
          "type": "integer"
        },
        "fonds_propres": {
          "type": "integer"
        },
        "ca_bilan": {
          "type": "integer"
        },
        "effectif_precis": {
          "type": "integer"
        },
        "resultat_net": {
          "type": "integer"
        },
        "resultat_exploitation": {
          "type": "integer"
        },
        "date_cloture": {
          "type": "string",
          "format": "date",
          "pattern": "^\\d{2}/\\d{2}/\\d{4}$",
          "description": "Format d/m/Y"
        },
        "radiate": {
          "type": "boolean"
        },
        "indice_risque_info_legal": {
          "type": "string"
        },
        "indice_risque_score3": {
          "type": "string",
          "description": "Score between 0-10"
        },
        "anne_indice_risque_score3": {
          "type": "string"
        },
        "nb_actionnaires": {
          "type": "integer"
        },
        "nb_filliales_directes": {
          "type": "integer"
        },
        "nb_filliales_indirectes": {
          "type": "integer"
        },
        "address": {
          "type": "string"
        },
        "zip": {
          "type": "string"
        },
        "city": {
          "type": "string"
        },
        "department": {
          "type": "string"
        },
        "country": {
          "type": "string"
        },
        "geo_lat": {
          "type": "number"
        },
        "geo_long": {
          "type": "number"
        },
        "telephone_number": {
          "type": "string"
        },
        "fax_number": {
          "type": "string"
        },
        "web_site": {
          "type": "string"
        },
        "url_maps": {
          "type": "string"
        },
        "url_viadeo\"": {
          "type": "string"
        },
        "url_twitter\"": {
          "type": "string"
        },
        "url_gnews\"": {
          "type": "string"
        },
        "url_wikipedia\"": {
          "type": "string"
        },
        "url_facebook\"": {
          "type": "string"
        },
        "url_linkedin\"": {
          "type": "string"
        },
        "url_score3\"": {
          "type": "string"
        },
        "url_scoopit\"": {
          "type": "string"
        },
        "logo_url\"": {
          "type": "string"
        },
        "email_contact\"": {
          "type": "string"
        },
        "contacts": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "name": {
                "type": "string"
              },
              "role": {
                "type": "string"
              }
            }
          }
        },
        "nb_actes": {
          "type": "integer"
        }
      }
    }
  ],
  "example": {
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
}
```

### #/components/schemas/Contact

```ts
{
  type?: string
  name?: string
  first_name?: string
  role?: string
}
```

### #/components/schemas/CompanyLightV2

```ts
{
  cccid?: string
  siren?: integer
  siret_siege?: integer
  raison_sociale?: string
  type_etablissement?: string
  appartient_groupe?: boolean
  adresse_complete?: string
  adresse_postale?: string
  code_postal?: string
  ville?: string
  last_modified?: string
  sigle?: string
  resume_activite?: string
  pays?: string
  radiee?: boolean
  nbre_signaux?: integer
  nbre_articles?: integer
  logo_url?: string
  links: {
    rel?: enum[self, blank]
    href?: string
  }[]
}
```

### #/components/schemas/CompanyV2

```ts
{
  "allOf": [
    {
      "$ref": "#/components/schemas/CompanyLightV2"
    },
    {
      "type": "object",
      "properties": {
        "nombre_etablissements_secondaires_inactifs": {
          "type": "integer",
          "nullable": true,
          "example": 3
        },
        "nombre_etablissements_secondaires_actifs": {
          "type": "integer",
          "nullable": true,
          "example": 30
        },
        "caractere_employeur": {
          "type": "boolean",
          "example": true
        },
        "enseignes": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 500,
          "example": null
        },
        "date_creation": {
          "type": "string",
          "format": "date",
          "nullable": true,
          "minLength": 0,
          "maxLength": 10,
          "example": "2010-01-05",
          "pattern": "^\\d{4}-\\d{2}-\\d{2}$"
        },
        "numero_tva": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": "FR43519570196"
        },
        "telephone": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": "04 82 53 99 00"
        },
        "departement_label": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "Rhône"
        },
        "departement": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 5,
          "example": "69"
        },
        "geo_lat": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": "45.769417"
        },
        "geo_long": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": "4.864512"
        },
        "secteur_activité_lies": {
          "type": "array",
          "items": {
            "type": "string"
          },
          "example": [
            "Cultures diverses",
            "Chimie minérale"
          ]
        },
        "code_ape_lies": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "code_ape": {
                "type": "string",
                "example": "01.11Z"
              },
              "code_ape_label": {
                "type": "string",
                "example": "Culture de céréales (à l'exception du riz), de légumineuses et de graines oléagineuses"
              }
            }
          },
          "example": [
            {
              "code_ape": "01.11Z",
              "code_ape_label": "Culture de céréales (à l'exception du riz), de légumineuses et de graines oléagineuses"
            },
            {
              "code_ape": "01.12Z",
              "code_ape_label": "Culture du riz"
            }
          ]
        },
        "code_ape": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 6,
          "example": "62.01Z"
        },
        "code_ape_brut": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 5,
          "example": "6201Z"
        },
        "code_ape_label": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 200,
          "example": "Programmation informatique"
        },
        "code_ape_complet": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 210,
          "example": "6201Z - Programmation informatique"
        },
        "forme_juridique_code": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 4,
          "example": "5710"
        },
        "forme_juridique": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "SAS société par actions simplifiée"
        },
        "type_entreprise": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": "PME"
        },
        "site_ecommerce": {
          "type": "boolean",
          "example": false
        },
        "activite_rd": {
          "type": "boolean",
          "example": false
        },
        "activite_export": {
          "type": "boolean",
          "example": false
        },
        "cac40": {
          "type": "boolean",
          "example": false
        },
        "startup": {
          "type": "boolean",
          "example": false
        },
        "secteur_industriel": {
          "type": "boolean",
          "example": false
        },
        "entreprise_fintech": {
          "type": "boolean",
          "example": false
        },
        "entreprise_familiale": {
          "type": "boolean",
          "example": false
        },
        "entreprise_b2c": {
          "type": "boolean",
          "example": true
        },
        "entreprise_b2b": {
          "type": "boolean",
          "example": true
        },
        "entreprise_biotech_medtech": {
          "type": "boolean",
          "example": false
        },
        "website": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": null
        },
        "url_twitter": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "https://twitter.com/@novaway"
        },
        "url_facebook": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "https://www.facebook.com/novawayfr/"
        },
        "url_linkedin": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "https://www.linkedin.com/company/novaway/"
        },
        "email_contact": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 100,
          "example": "contact@novaway.fr"
        },
        "code_confidentialite": {
          "type": "boolean",
          "example": true
        },
        "avertissement_bilan": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 150,
          "example": "les bilans étant confidentiels ou non disponibles nous ne pouvons afficher toutes les données chiffrées"
        },
        "subventions_investissements": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "participation_bilan": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "resultat_bilan": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "resultat_net_consolide": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "dotations_amortissements": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 23456789
        },
        "ca_consolide": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "resultat_exploitation": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "ca_bilan": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "impots_taxes": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "effectif_sous_traitance": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "charges_financieres": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "salaires_traitements": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "ca_export": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "ca_france": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 123456789
        },
        "effectif": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 10
        },
        "fonds_propres": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 529033
        },
        "capital_social": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 13500
        },
        "duree_exercice": {
          "type": "integer",
          "nullable": true,
          "minLength": 0,
          "maxLength": 20,
          "example": 12
        },
        "annee_cloture_exercice": {
          "type": "string",
          "nullable": true,
          "minLength": 0,
          "maxLength": 4,
          "example": "2020"
        },
        "date_cloture_exercice": {
          "type": "string",
          "format": "date",
          "nullable": true,
          "minLength": 0,
          "maxLength": 10,
          "example": "2020-12-31",
          "pattern": "^\\d{4}-\\d{2}-\\d{2}$"
        },
        "contacts": {
          "type": "array",
          "items": {
            "$ref": "#/components/schemas/Contact"
          }
        }
      }
    }
  ],
  "example": {
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
}
```