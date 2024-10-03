---
title: Decidento API Documentation

#language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
#  - shell
#  - ruby
#  - python
#  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - authentification
  - articles
  - companies
  - signals
  - schemasignaux
#  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Decidento API
---

# Documentation Decidento API 

Bienvenue sur l'API DECIDENTO ! Vous pouvez utiliser l'API pour accéder aux différents points (endpoints) de Decidento, qui permettent de récupérer des informations sur divers Articles, Entreprises, Signaux, et Contacts présents dans notre base de données.

Pour utiliser l'API Decidento, consultez la [section d'authentification](#authentification) et rendez-vous sur <a href="https://api.decidento.com/" target="_blank" rel="noopener noreferrer">API Decidento</a> pour tester.
## Path Table

> La structure de la réponse Json va être affiché dans cette section !

<style>
  .method-get {
    color: green;
    font-weight: bold;
  }
</style>

| Method | Path                                                        | Description                             |
| --- |-------------------------------------------------------------|:----------------------------------------|
| <span class="method-get">GET</span> | [/articles](#get-all-articles)                              | Obtenir les derniers articles           |
| <span class="method-get">GET</span> | [/articles/search](#search-for-list-of-articles)            | Rechercher une liste d'articles        |
| <span class="method-get">GET</span> | [/articles/search](#search-for-list-of-articles)            | Trouver un article par ID              |
| <span class="method-get">GET</span> | [/articles/collection](#find-collection-of-articles-by-id)  | Trouver une collection d'articles par IDS |
| <span class="method-get">GET</span> | [/companies](#get-all-companies)                            | Rechercher des entreprises avec des paramètres |
| <span class="method-get">GET</span> | [/companies/{companyId}](#find-company-by-id)              | Trouver une entreprise par ID          |
| <span class="method-get">GET</span> | [/companies/collection](#find-list-of-companies-by-ids)    | Trouver une collection d'entreprises par IDS |
| <span class="method-get">GET</span> | [/companies/v2](#find-list-of-companies)                   | Rechercher des entreprises avec des paramètres |
| <span class="method-get">GET</span> | [/companies/{companyCccid}/v2](#find-company-by-its-unique-identifier-cccid) | Trouver une entreprise par CCCID       |
| <span class="method-get">GET</span> | [/companies/collection/v2](#find-a-collection-of-companies-by-their-siren) | Trouver une collection d'entreprises par SIREN |
| <span class="method-get">GET</span> | [/signals](#get-last-signals)                               | Obtenir les derniers signaux           |
| <span class="method-get">GET</span> | [/signals/{signalId}](#get-a-signal-by-id)                 | Trouver un signal par ID               |
| <span class="method-get">GET</span> | [/signals/collection](#get-a-list-of-signals-by-ids)       | Trouver une collection de signaux par IDS |
