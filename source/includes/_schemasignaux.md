# Signals Schemas

## Signal_A
### id
- **Type :** integer($int64)

### last_article_pubdate
- **Type :** string($date)
- **Pattern :** ^\d{2}/\d{2}/\d{4}$
- **Exemple :** 26/03/2021
- **Description :** Date de publication du dernier article (dd/mm/YYYY)

### creation_date
- **Type :** string($date)
- **Pattern :** ^\d{2}/\d{2}/\d{4}$
- **Exemple :** 26/03/2021
- **Description :** Date de création du signal (dd/mm/YYYY)

### last_update
- **Type :** string($date)
- **Pattern :** ^\d{2}/\d{2}/\d{4}$
- **Exemple :** 26/03/2021
- **Description :** Date de mise à jour du signal (dd/mm/YYYY)

### follow_date
- **Type :** string($date)
- **Pattern :** ^\d{2}/\d{2}/\d{4}$
- **Exemple :** 26/03/2022
- **Description :** Date de mise à jour du statut suivi du signal (dd/mm/YYYY)

### type *
- **Type :** string

### label_type
- **Type :** string

### status
- **Type :** string
- **Description :** Order Status
- **Enum :** 
  - Détecté
  - Suivi
  - Terminé

### company_main
  - **CompanyLight :**
    - **id**
      - **Type :** integer
      - **Exemple :** 72242
    - **siren**
      - **Type :** integer
      - **MinLength :** 9
      - **MaxLength :** 9
      - **Pattern :** ^\d{9}$
      - **Exemple :** 831946488
    - **siret**
      - **Type :** integer
      - **MinLength :** 14
      - **MaxLength :** 14
      - **Pattern :** ^\d{14}$
      - **Exemple :** 83194648800010
    - **social_name**
      - **Type :** string
      - **Exemple :** OPEN TOURISME LAB NIMES METROPOLE
    - **siege**
      - **Type :** boolean
      - **Exemple :** true
    - **links**
      - **Type :** array
      - **rel**
        - **Type :** string
        - **Exemple :** self
        - **Enum :** [self, blank]
      - **href**
        - **Type :** string
        - **Exemple :** https://api.decidento.com/companies/2438
    - **sirets**
      - **siret :**	string
        - **example :** 83194648800123
      - **cp	:** string
      - **example :** 75019
