![logo de la Wild Code SChool en exemple](Ressources/logo_WCS.jpg)

## Sommaire 

# [📜 Introduction](#introduction)

- Utilisation des logiciels John-the-ripper et hashcat afin de tester la robustesse de mots de passe sur un poste client. 
Ces tests sont exécutés via des VM, une machine serveur et une client.

# [🎯 Présentation du projet](#presentation-du-projet)

- Hacker le mot de passe d'un fichier zip à l'aide de deux logiciels.
- Le projet présenté a pour but d'utiliser les logiciels John-the-ripper et hashcat afin de tester la robustesse des mots de passe depuis un poste client. 
Ces tests sont exécutés sur des VM et nous permettront de comparer les logiciels.

## <ins>Présentation John-the-ripper et Hashcat<ins>

### <ins>I/Qu'est-ce que John-the-ripper?<ins>

 John-the-ripper est un logiciel de cassage de mots de passe utilisé pour tester la robustesse des mots de passe. Il a d'abord été développer pour tourner sous des 
 systèmes dérivés d'UNIX mais le programme fonctionne aujourd'hui sous d'autres plateformes comme FreeBSD (A COMPLETER)
 Il est l'un des logiciels les plus populaires car il inclut une autodétection des fonctions de hachage utilisée pour stocker les mots de passe. (Fonction de 
 hachage: une fonction mathématique qui brouille les données pour les rendre illisibles).

### <ins>II/Qu'est-ce que Hashcat?<ins>
 

Source [Wikipédia](https://fr.wikipedia.org/wiki/John_the_Ripper) 


 # [👥 Membres du groupe par sprint](#membres-du-groupe-par-sprint)
  
 # [⚙️ Choix Techniques](#choix-techniques)

 ### <ins>Pourquoi choisir John-the-ripper?<ins>
  
- John-the-ripper à plusieurs modes d'action. Les plus fréquentes sont les méthodes:
  
+ simple (utilisation du nom utilisateur pour casser les mots de passe les plus simples)
+ Par dictionnaire (utilise une liste de mots en utilisant aussi le nom utilisateur)
+ Incrémental il essayera toutes les combinaisons possibles

Bien évidemment, plus un mot de passe est compliqué, plus sa recherche sera longue.

John-the-ripper peut casser des mots de passe avec différentes fonctions de hachage avec des algorithmes comme MD5, blowfish, Kerberos, AFS, et les LM hashes de Windows NT/2000/XP/2003. 
On peut le complèter avec des modules additionnels pour qu'il puisse casser des mots de passe basés sur les hash MD4 ainsi que MySQL, LDAP, NTLM.

Pour faire la liaison avec Hashcat, Zip2john permet d'extraire le hash que nous avons besoi pour hashcat

Source [Wikipédia](https://fr.wikipedia.org/wiki/John_the_Ripper) 

 ## <ins>Installation de John-the-ripper<ins>

Sur une machine Ubuntu, via le terminal nous allons utiliser les commandes suivantes:

  > sudo snap install john-the-ripper

![Installation John-the-ripper](Ressources/Installation_John-the-ripper.png)

Ensuite nous allons chercher l'endroit où si situe notre logiciel et nous y rendre

  > which john-the-ripper (d'autres touches comme  "find" ... sont possibles)

![Which John-the-ripper](https://github.com/user-attachments/assets/cbb122d4-6d20-40d8-b1a2-76771b48aa51)

 Se deplacer dans le dossier bin
  
  > cd /snap/bin

 et pour découvrir l'ensemble du contenu nous ferons 
 
  > ls 

et nous trouverons tous les modules john-the-ripper installés.
  
![Trouver John-the-ripper](https://github.com/user-attachments/assets/eb3f5806-5731-4913-a2b1-850836f8fccc)
 

Pour activer celui que nous voulons, nous ferons

  > ./john-the-ripper.zip2john

![Activer john2zip](https://github.com/user-attachments/assets/ec2e1363-c358-42b9-8921-e582952bb457)
  
Ensuite, nous allons extraire le hash et pour cela, nous allons nous rendre dans le dossier où se trouve notre fichier zip

  > + cd /
  > + pwd (pour voir où nous sommes)
  > + cd /home/wilder

 ![Retour dossier fichier zip](https://github.com/user-attachments/assets/a191a7e7-6001-452f-9c20-5e16e8472751)
 
Une fois dans le dossier en question, nous exécuterons la commande

  > john-the-ripper.zip2john (fichier.zip) > hash.txt

Rien ne s'affiche c'est pour cela que nous ferons la commande suivante

Vérifier que le hash est bien dans le fichier  

  > cat hash.txt

![Vérifier hash dans le fichier](https://github.com/user-attachments/assets/1c389c1e-d4c8-4e28-8680-338d39ca4fb2)

et enfin, l'extraire avec

  > john hash.txt pour finir
  
![Extraire et trouver le code](https://github.com/user-attachments/assets/15130bc1-1ef3-4be0-8347-74b19ce52013)


(En cours d'écriture)

 # [🧗Difficultés rencontrées](#difficultes-rencontrees)
 # [💡 Solutions trouvées](#solutions-trouvees)
 # [🚀 Améliorations possibles](#ameliorations-possibles)


**Objectifs finaux**


# 👥 Membres du groupe par sprint
<span id="membres-du-groupe-par-sprint"></span>
**Sprint 1**

| Membre   | Rôle       | Missions |
| -------- | ---------- | -------- |
| Tatiana  | PO         | -        |
| Bertrand | SM         | -        |
| Sheldon  | Technicien | -        |
| Greg     | Technicien | -        |

**Sprint 2**

| Membre   | Rôle       | Missions |
| -------- | ---------- | -------- |
| Bertrand | PO         | -        |
| Sheldon  | SM         | -        |
| Tatiana  | Technicien | -        |

