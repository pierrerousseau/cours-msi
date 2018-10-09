# cours-msi


# usage local

## Installer reveal.js

    $ npm install

## Installer Grunt

    $ npm install grunt
    $ npm install grunt-cli

## Lancer le serveur de dev

    $ grunt serve

## Créer le pdf de cours

    $ pandoc -r markdown_github -o cours/cours.pdf cours/cours.md

Puis se rendre sur http://localhost:8000/