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

>Para Docker File

como crer la imagen de docker de cypress

* docker build mi-nombre:v1 .
 docker build cypress-azuredevops:v1

* Ejecutar una carpeta en especial

> docker run -i -v "$PWD":/my-cypress-project -t cypress-azuredevops:v1 --spec cypress/integration/pom/*.js
 
 Expliquemos cada flag

    * "$PWD" directorio donde esta el folder

    * /my-cypress-project WORKDIR creando en el DockerFile

    * cypress-azuredevops:v1 nombre de la imagen creada

    * --spec cypress/integration/pom/*.js  ruta de la carpeta de los casos a ejecutar
