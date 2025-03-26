![logo de la Wild Code SChool en exemple](Ressources/logo_WCS.jpg)


# [📜 Introduction](#introduction)

Vous êtes de ces personnes qui oublient ou perdent leurs mots de passe 🔑 ou simplement curieuses?! ALors ce qui suit est fait pour vous! 
Voici deux logiciels qui vous permettront de récupérer des mots de passe sur différents types fichiers.


# [🎯 Présentation du projet](#presentation-du-projet)

Le projet présenté a pour but d'utiliser les logiciels John-the-ripper et hashcat afin de récupérer un mot de passe sur des types de fichiers différents (sur cette présentation, les fichiers seront des .zip) mais ils peuvent aussi contribué à tester la robustesse de mots de passe.
Ces tests seront exécutés sur des VM qui nous permettront de comparer les logiciels.

  
## <ins>Présentation John-the-ripper et Hashcat<ins>

### <ins>I/Qu'est-ce que John-the-ripper?<ins>

John-the-ripper est un logiciel de cassage de mots de passe utilisé pour tester la robustesse ceux-ci. Il a d'abord été développer pour tourner sous des 
systèmes dérivés d'UNIX mais le programme fonctionne aujourd'hui sous d'autres plateformes. Il est l'un des logiciels les plus populaires.
John-the-ripper peut casser des mots de passe avec différentes fonctions de hachage avec des algorithmes comme MD5, blowfish, Kerberos, AFS. On peut le complèter avec des modules additionnels pour qu'il puisse casser des mots de passe basés sur les hash MD4 ainsi que MySQL, LDAP.
> Pour plus d'informations: [Wikipédia](https://fr.wikipedia.org/wiki/John_the_Ripper#)  [John-the-ripper](https://www.openwall.com/john/doc/)


### <ins>Pourquoi choisir John-the-ripper?<ins>
  
L'une des raisons qui vous ferez choisir John-the-ripper est la facilité de sa prise en main et de sa compréhension d'utilisation. Il a un mode automatique du lancement de ses attaques. C'est à dire qu'il lancera de lui meême ses différentes attaques sans que vous ne fassiez quoi que ce soit.
John-the-ripper à plusieurs modes d'actions. Les plus fréquentes sont les méthodes:
  
+ Attaque simple: Utilisation du nom utilisateur pour casser les mots de passe les plus simples.
+ Attaque Par dictionnaire: Utilise une liste de mots en utilisant aussi le nom utilisateur.
+ Attaque Incrémental: Il essayera toutes les combinaisons possibles.

> NB: Plus le mot de passe est complexe, plus sa recherche sera longue.


### <ins>II/Qu'est-ce que Hashcat?<ins>

 
Hashcat est un logiciel de récupération de mot de passe. Il disposait d'une base de code propriétaire jusqu'en 2015, mais part la suite a été publier en tant que logiciel open source. Tout comme John-the-ripper, il est disponible sur différentes plateformes. Il dispose d'un énorme avantage par rapport à ses concurrents car il exploite la puissance des cartes graphiques (GPU) pour accélérer le processus et lui permettre de retourver des mots de passe bien plus rapidement qu'avec un simple processeur comme le fait John-the-ripper.

### <ins>Pourquoi choisir Hashcat?<ins>

Plusieurs types d'attaques sont possibles avec Hashcat:

+ Attaque par force brute "simple": Attaque efficace mais très lente même en utilisant la puissance du GPU car il va tester **toutes** les combinaisons de caractères possible jusqu'à trouver la bonne.
+ Attaque par dictionnaire: Attaque qui semble être la plus rapide. Le loggiciel teste des mots de passe issus d'une liste prédéfinie (comme Rockyou.txt que l'on peut retourver chez John-the-ripper) et voir s'il y a une correspondance. Méthode qui peut être redoutablement efficace face aux mots de passe les plus utilisés.
+ Attaque par masque: Cette attaque est idéale **si** l'on connaît par partie du mot de passe à cracker. Hashcat testera les différentes possibilités de mots de passe en se basant sur les caractéristiques entrées.
+ Attaque hybride: C'est un mix entre l'attaque par dictionnaire et par force brute simple. Il utilisera une liste de mots de passe pour la tester en y rajoutant des variantes (majuscules, chiffres..)
+ Attaque combiantoire: 2 dictionnaires différents sont combinés pour tester une grande variété de mots de passe. Par exemple, la liste la plus longue des prénoms avec la listes la plus longue des mots le plus utlisés. Hashcat s'e servira des deux listes, les associera pour combiner les plus de mots de passe possibles.

> Pour plus d'informations: [Hashcat](https://www.jedha.co/formation-cybersecurite/hashcat-l-outil-gratuit-pour-tester-les-mots-de-passe)

 # [👥 Membres du groupe par sprint](#membres-du-groupe-par-sprint)
**Sprint 1**

| Membre   | Rôle       | Missions |
| -------- | ---------- | -------- |
| Tatiana  | PO         | Installer et comprendre le fonctionnement du logiciel John-the-ripper/ Commencer la documentation 'README.md'|
| Bertrand | SM         | Installer et comprendre le fonctionnement du logiciel John-the-ripper/ Commencer la documentation 'User_guide.md'|
| Sheldon  | Technicien | Installation des machines virtuelles et les mettre en réseaux/ Commencer la documentation 'Install.md'|
| Greg     | Technicien | Installation des machines virtuelles et les mettre en réseaux.|



# 👥 Membres du groupe par sprint
<span id="membres-du-groupe-par-sprint"></span>
**Sprint 2**

| Membre   | Rôle       | Missions |
| -------- | ---------- | -------- |
| Bertrand | PO         | Recherche sur utilisation et installation de hashcat/ Continuer la documentation 'User_guide'/ Tests de démos Logiciels|
| Sheldon  | SM         | Recherche sur utilisation et installation de hashcat/ Continuer la documentation 'Install.md'/ Commencer le PowerPoint|
| Tatiana  | Technicien | Recherche sur utilisation et installation de hashcat/ Continuer la documentation 'README.md/ Relecture de l'ensemble des documents.|
  
 # [⚙️ Choix Techniques](#choix-techniques)

Mise à disposition de deux machines virtuelles.

Une machine serveur windows 2022:
 -  Configuration d'un réseau interne afin d'être relié à la machine client (UBU01).
 -  Création des fichiers.zip sur cette VM
   
Une machine client sur une distribution ubuntu:
 -  Configuration d'un réseau interne afin de se connecter au serveur Windows (SRVWIN01).
 -  Installation, test et exécution des logiciels sur la VM client.
   
Les attaques:
 - Depuis VM client (UBU01). Récupération des fichiers .zip sur le serveur (SRVWIN01)
 - Exécution des logiciels depuis la VM client. 

 # [🧗Difficultés rencontrées](#difficultes-rencontrees)[💡Solutions trouvées](#solutions-trouvees)
 

|  [🧗Difficultés rencontrées](#difficultes-rencontrees)|[💡Solutions trouvées](#solutions-trouvees)|  
| --------------------------------------- | --------------------------------------- |
| Installation du logiciel avec Apt install ne fonctionne pas.| Installation du logiciel avec Snap install.|
| Trouver le logiciel et l'activer.| Recherches menées via des articles et vidéos de démonstration.|
| Compréhension d'utilisation logiciel et sa prise en main.| De nombreuses recherches et de tests pour enfin réussir à comprendre et l'utliser.|
| Récupérer un fichier .Zip d'un serveur à une VM client.| Mise en réseau des machines ainsi qu'une copie du fichier concerné.|
| Matériel pas assez puissant pour effectuer certains tests| Choix d'opter pour des tests réalisables et efficaces.|


💡 La meilleure solution dans tous ces cas de figures a été de travailler par groupe de deux, afin d'avancer ensemble et de partager nos avancées. 



