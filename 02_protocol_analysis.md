# Analyse des protocoles

## Objectif

Identifier les principaux protocoles utilisés sur le réseau afin de caractériser les types d’activités observées et de repérer les protocoles présentant un intérêt pour l’analyse forensic.

## Méthode
    L'analyse a été réalisée à l'aide de l'option : Statistics > Protocol heirarchy

    Cette fonctionnalité permet d’obtenir une vue hiérarchique des protocoles présents dans la capture ainsi que leur répartition en nombre de paquets et en volume de données.

# Résultats
![protocols heirarchy](captures\protocoles_hierarchy_stat.png)

    Le trafic réseau est majoritairement basé sur le protcole TCP, représentant plus 95 % du volume de données échangées.

    Les pricipaux protocoles applicatifs identifiés sont :
    🔹HTTP : Représente une part importante du volume de données, avec environ 47 % des bytes total des données échangées.
    Ce trafic correspond principalement à la navigation web, au chargement de ressources web (images, feuilles de style) ainsi qu’au téléchargement de fichiers.
    
    La présence de HTTP non chiffré permet d’observer le contenu des requêtes et réponses en clair.

    🔹TLS : Utilisé pour sécuriser une partie des communications réseau, avec environ 24 % des bytes, notamment dans le cadre de connexions HTTPS.

    Le chiffrement empêche l’accès direct au contenu des échanges, mais certaines métadonnées restent observables ; adresses IP, noms de domaine (SNI), certificats et volumes de trafic.

    🔹FTP : Le protocole FTP est également présent dans la capture.
    Ce protocole transmet les données et les identifiants sans chiffrement, ce qui permet :

        - l’observation des commandes FTP,
        - l’identification des authentifications,
        - l’extraction de fichiers transférés,
        - ainsi que l’analyse du contenu des échanges.

    Ce protocole constitue un point d’intérêt important dans le cadre d’une investigation forensic.
   
    🔹Protocoles secondaires : D’autres protocoles réseau ont également été identifiés : 
        🔹 NTP : Synchronisation horaire des systèmes.
        🔹 SSDP : Découverte de services et d'équipement sur le réseau local.
    
    Ces protocoles correspondent à des activités système classiques dans un environnement réseau standard.

## Interprétation
Le trafic observé correspond à un usage mixte du réseau incluant :
- navigation web
- communications sécurisées
- transferts de fichiers
- activités système (mises à jour)

La présence simultanée de :
    -> trafic HTTP non chiffré 
    -> et de communications FTP en clair,
constitue un point d’intérêt majeur pour l’analyse forensic, permettant potentiellement l’extraction de données sensibles (identifiants, fichiers).

## Conclusion

L’analyse des protocoles met en évidence un environnement réseau hétérogène combinant des usages utilisateurs classiques, des communications système et des échanges non chiffrés exploitables dans le cadre d’une investigation forensic.

Les protocoles HTTP et FTP apparaissent comme les principales sources d’informations exploitables pour la suite de l’analyse.