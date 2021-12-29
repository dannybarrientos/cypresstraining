Ejecutar con Tags, Utilizamos la libreria cypress-grep/
Para ejecutar con Grep se ejecuta de varias forma

Forma 1 Este busca la palabra en el descripcion
> describe('Button Actions (regression)', { tags: '@regressionTag' },() => {

npx cypress run --spec cypress/integration/tags/*.js --env grep= "regression"


Forma 2 Este busca en archivos los nombre del tags
En este ejemplo ejecutare todos menos los de regresionTag, si en un describe se encuentra en regresionTag con otro Tag, este no se ejecutara

npx cypress run --spec cypress/integration/tags/*.js --env grepTags=-@regressionTag

Ejecutar los tags que contenga estos Tags

npx cypress run --spec cypress/integration/tags/*.js --env grepTags='@regressionTag+sanityTag'


Para validar que un elemento es CaseSensity
cypress/integration/variables-aliases/var-alias.spec.js
{matchCase: false})

> Los Alias no funciona con los "arrow function" => () =>{} se debe de cambiar la sintaxis por los functions
