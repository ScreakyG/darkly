# definition

ht → abréviation historique de “hypertext / HTTP” utilisée par Apache.

.htpasswd → fichier utilisé par Apache pour stocker des couples utilisateur:mot-de-passe (haché) afin de protéger l’accès à un dossier via authentification HTTP Basic

# explaination

if we look up at `localhost:8080/robots.txt` we can find a `/whatever/` path. when we check it, we get a `htpasswd` file. its a 32 character md5 hash. when decrypted you get the password `qwerty123@` when used on the root/admin page `localhost:8080/admin/` you get the flag

# risk

- complete control of the website - acces root
- can compromise user
- inject malware, cron, website redirection, phishing
- server access, db access

# fix 

- never stock .htpasswd in web folder
- don't use robots.txt to hide things
- explicitely hide *.ht file in the webserver
- don't user root or admin as a login
