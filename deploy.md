# Deployment de l'application Cloud

# Rapport de déploiement - [VOTRE NOM]

## Liens- **Application en ligne :** [https://cloud-project-deploiment.osc-fr1.scalingo.io/]
- **Dépôt de code :** [https://github.com/Chris-hir-gall/eval-deploy-scalingo.git]

## Prérequis techniques ...... 
    php 8.2
    composer instalée
    
    un compte scalingo
    un repository github
    lier le repository avec un project scalingo
    scalingo deploie a partir des workflows
    

## Fichier de configuration CI ...... 
    # Le nom de ton assistant
name: Verification du Projet Cloud, deploiment sur scalingo

# Quand doit-il travailler ?
on:
  - push
# Dès que tu envoies du code sur Github

# Qu'est-ce qu'il doit faire ?
    jobs:
    verification-basique:
        runs-on: ubuntu-latest  # Il utilise un ordinateur sous Linux

        steps:
        - name: Recuperer le code
            uses: actions/checkout@v4
            # Il fait un "copy-paste" du code

        - name: Installer PHP
            uses: shivammathur/setup-php@v2
            with:
            php-version: '8.2'
            # Il installe la même version que toi

        - name: Verifier l'installation
            run: composer install
            # Il vérifie que tout fonctionne

## Procédure de déploiement pas à pas ( ⚠ Rien concernant la base de données )

    lier un repository github avec un project scalingo, completer lapplication
    et faire un commit puis un push, seulement si l'action du workflow est
    reussie, scalingo lance le deploiment. 
    modifier les variables de environement chez scalingo
        APP_ENV avec une valeur prod
        APP_SECRET avec une valeur generé = 295cc6408ca1a76c96a12879c7b502c3
    
