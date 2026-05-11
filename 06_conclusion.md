# Timeline et conclusion de l’investigation

## Timeline des événements observés

| n° | Événement analysé | Résultats observés |
|----|-------------------|-------------------|
| 1 | Identification du réseau local | Réseau LAN de type 192.168.250.x/24 |
| 2 | Machines détectées | 192.168.250.132, .133, .134, .136 |
| 3 | Systèmes identifiés | Windows 10 et Linux (Debian/Ubuntu) |
| 4 | Activité utilisateur détectée | Navigation web depuis 192.168.250.133 |
| 5 | Site web visité | www.phpbb-fr.com |
| 6 | Authentification HTTP observée | Transmission d’identifiants en clair via requête POST |
| 7 | Fichier téléchargé | lang_fr-3.3.0.zip |
| 8 | Validation du téléchargement | Réponse HTTP 200 OK |
| 9 | Extraction du fichier | Export via "Export Objects → HTTP" |
| 10 | Analyse du fichier ZIP | Archive légitime de langue phpBB |
| 11 | Détection d’activité suspecte | Multiples tentatives FTP USER/PASS |
| 12 | Type d’attaque identifié | Attaque par brute force FTP |
| 13 | Machines impliquées | 192.168.250.134 et 192.168.250.136 |
| 14 | Cible de l’attaque | Serveur FTP : 192.168.250.132 |
| 15 | Authentification réussie | USER admin1 / PASS admin |
| 16 | Action post-compromission | Accès au répertoire /home/admin1/Documents/ |
| 17 | Fichier exfiltré | hskapsce |
| 18 | Analyse du contenu exfiltré | Listing de répertoires Linux |
| 19 | Nature des données récupérées | Informations système et structure utilisateur |

## Conclusion générale

| Élément | Conclusion |
|----------|-------------|
| Type de réseau | Réseau local (LAN) comportant plusieurs hôtes actifs |
| Nombre de machines identifiées | 4 machines principales |
| Systèmes d’exploitation observés | Windows 10 et Linux (Debian/Ubuntu) |
| Protocoles principaux | TCP, HTTP, TLS, FTP |
| Activité utilisateur identifiée | Navigation web sur phpBB depuis 192.168.250.133 |
| Activité système identifiée | Mises à jour Linux, Snapcraft, dépôts Debian/GNOME |
| Type d’attaque détectée | Brute force FTP |
| Méthode d’attaque | Enumeration d’identifiants + attaque par dictionnaire |
| Comptes compromis | admin1 / admin |
| Machine cible | 192.168.250.132 |
| Machines suspectes | 192.168.250.134 et 192.168.250.136 |
| Données exfiltrées | Fichier hskapsce |
| Nature du fichier exfiltré | Listing système Linux |
| Niveau de sévérité | Moyen |
| Impact observé | Compromission FTP suivie d’une collecte d’informations |
| Indicateurs de compromission | Échecs FTP répétés, connexions automatisées, exfiltration de fichier |
| Faiblesse de sécurité identifiée | Utilisation de protocoles non chiffrés (HTTP/FTP) |

## Conclusion finale

Cette investigation a permis de reconstituer les principales activités réseau présentes dans le dump analysé.

L’analyse met en évidence :
- une activité utilisateur classique de navigation web,
- des communications système légitimes,
- ainsi qu’une attaque par brute force FTP ayant abouti à une compromission réussie.

L’exploitation du protocole FTP en clair a permis d’observer directement les identifiants utilisés et les actions réalisées après authentification.

Le fichier exfiltré ne contient pas de données sensibles critiques, mais révèle une phase de reconnaissance système effectuée après compromission.

Cette étude illustre l’importance :
- du chiffrement des communications réseau,
- de l’utilisation de mots de passe robustes,
- de la surveillance des tentatives d’authentification répétées,
- et de l’analyse forensic réseau dans la détection des comportements malveillants.
