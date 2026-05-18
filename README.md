Généralités :
-------------
On réalise ici une PWA (Progressive Web App).
Pour faire simple, c'est un site internet conçu pour se comporter exactement
comme une application mobile classique, mais sans avoir besoin de la télécharger
depuis le Google Play Store ou l'App Store d'Apple.

Cette application doit être hébergée sur un site accessible en https. Cependant, le serveur web
https://choraleknds.42web.io/ a un comportement qui bloque l'installation et ne permet qu'un
simple raccourci sur l'écran d'accueil du téléphone. C'est pourquoi j'utilise les GitHub Pages.

La GitHub Page de l'application Bose : https://github.com/Tebounet/Bose
Télécharger le code dans le répertoire courant : git clone https://github.com/tebounet/Bose.git .
L'url de l'application : https://tebounet.github.io/Bose/ ; c'est cette url qui donne accès
à l'application et permet de l'installer.

Le fichier html contient le code, index.html est plus professionnel qu'un autre nom.
Fichier manifest.json
Fichier sw.js
Fichier vexflow.js : en local plutôt que sur internet, pour permettre de travailler hors réseau
Fichier .htaccess : force à rester en https (c'était un essai pour héberger sur https://choraleknds.42web.io/ )


1) GITHUB / Création du repository :
------------------------------------
1.1) soit sur le site GitHub
	Laissez-le en Public.
	Ne cochez aucune case (ni README, ni .gitignore).
	Cliquez sur Create repository.
1.2) soit dans une fenêtre cmd à partir d'un répertoire vide
	echo "# Bose" >> README.md
	git init
	git add README.md
	git commit -m "first commit"
	git branch -M main
	git remote add origin https://github.com/Tebounet/Bose.git
	git push -u origin main
1.3) soit dans une fenêtre cmd à partir d'un répertoire contenant les fichiers de l'application
	git init
	git add .
	git commit -m "Premiere version"
	git branch -M main
	git remote add origin https://github.com/Tebounet/Bose.git
	git push -u origin main

2) GITHUB / Activation de l'application :
-----------------------------------------
Important : dans GitHub, Settings > Pages, et sous "Build and deployment" :
	. choisir la branche main
	. vérifier que le dossier est sur /(root)
	. cliquer sur Save

ASTUCES :
--------
	- Pour ne pas avoir de message de warning sur la conversion des fins de lignes :
		git config --global core.autocrlf true
	- Un fichier README.md permet une meilleure mise en page qu'un fichier readme.txt

APRES UNE MISE A JOUR DU CODE :
-------------------------------
	git add .
	git commit -m "modification du code"
	git push origin main
	
INSTALLATION COMME APPLICATION :
--------------------------------
- ouvrir Google Chrome (sur smartphone ou PC), Safari sur IPhone 
- aller à l'URL https://tebounet.github.io/Bose/
- l'application est alors visible mais pas installée
- dans le menu de Chrome (les trois petits points en haut ou bas de page), cliquer sur
  "Ajouter à l'écran d'accueil" ; 2 choix sont alors possibles, cliquer sur "Installer"

Remarque 1 : l'application une fois installée s'appelle "Chanter les notes" (cela est déterminé
		   par le fichier manifest.json) alors que sur smartphone son nom est "solfier" dans la
		   liste des applications --> à unifier
		   
Remarque 2 : le fichier index.html doit contenir la ligne suivante juste avant </head> :
				<link rel="manifest" href="manifest.json">