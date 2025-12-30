# Définition d’une attaque path traversal


Une attaque path traversal ou directory traversal vise à accéder et lire des fichiers stockés en dehors de l’arborescence exposée directement par le service web.

Il s’agit de modifier des paramètres d’une requête pour naviguer dans l’arborescence. Le but de l’attaquant est de parcourir les répertoires afin d’atteindre des fichiers sensibles auxquels l’accès est normalement refusé (fichiers de configuration, code source…)

Dans certaines situations, l’attaquant a même parfois accès à des fonctionnalités non autorisées, comme l’écriture de fichiers sur le serveur. Cela peut l’amener à prendre le contrôle du serveur et la vulnérabilité devient alors une RCE.



# vulnerabilite


le site est vulnerable au path traversel car si on rentre '../' derriere 'page=<xxx>' on est prompt par un message et si on continue encore avec '../../' d'autre message jusqua arriver au message `you can do it!` a partir de la on peux tester differente combinaison de fichier, si on essaye de recup le password on a le flag qui pop

localhost:8080/index.php?page=../../../../../../../../../../../etc/passwd

# risk

c'est une vulnerabilite car on peut acceder a different dossier sensible (confif, logs, system file, ou secret pw)


# fix

faire une whitelist des fichiers autorises, forcer un dossier racine (sandbox)
