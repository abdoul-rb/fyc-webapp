# calculateur-impot

> Formulaire permettant de calculer l&#39;impôt que l&#39;on va payer pour l&#39;année courante

**Test avec Jest**


## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```
## Variables
`RATES_2021`             : Palier d'imposition d'une année: Max de la tranche de revenu, avec le taux d'imposition associé
`taxableIncome`          : Revenu net imposable
`incomeAfterTaxable`     : Revenu après impôt
`taxAmount`              : Montant de l'impôt
`taxPercentage`          : Pourcentage d'imposition
`nbOfKids`               : Nombre d'enfants du foyer
`nbOfKidsWithCMI`        : Nombre d'enfants bénéficiant de la CMI
`isMarried`              : Etes-vous marié ?
`householdPart`          : Nombre de parts du foyer fiscal
`familyIncome`           : Quotient familial

Le fichier formulas.js contient les fonctions à tester

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
