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
  - articles
  - companies
  - signals
#  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Decidento API
---

# Decidento API documentation

Welcome to the DECIDENTO API ! You can use our API to access Decidento endpoints, which can get information on various Articles, Companies, and Signals in our database.

We have language bindings in Shell, PHP, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with <a href="https://api.decidento.com/" target="_blank" rel="noopener noreferrer">API Decidento</a>.

## Path Table

> Json response structure will be displayed in this section !

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
| <span class="method-get">GET</span> | [/articles/search](#search-for-list-of-articles)                | Find article by ID                      |
| <span class="method-get">GET</span> | [/articles/collection](#find-collection-of-articles-by-id)  | Find a collection of articles by IDS    |
| <span class="method-get">GET</span> | [/companies](#get-all-companies)                            | Search companies with parameters        |
| <span class="method-get">GET</span> | [/companies/{companyId}](#find-company-by-id)            | Find company by ID                      |
| <span class="method-get">GET</span> | [/companies/collection](#find-list-of-companies-by-ids)            | Find a collection of companies by IDS   |
| <span class="method-get">GET</span> | [/companies/v2](#find-list-of-companies)                            | Search companies with parameters        |
| <span class="method-get">GET</span> | [/companies/{companyCccid}/v2](#find-company-by-its-unique-identifier-cccid) | Find company by CCCID                   |
| <span class="method-get">GET</span> | [/companies/collection/v2](#find-a-collection-of-companies-by-their-siren)       | Find a collection of companies by SIREN |
| <span class="method-get">GET</span> | [/signals](#getsignals)                                     | Get last signals                        |
| <span class="method-get">GET</span> | [/signals/{signalId}](#getsignalssignalid)                  | Find signal by ID                       |
| <span class="method-get">GET</span> | [/signals/collection](#getsignalscollection)                | Find collection of signals by IDS       |
