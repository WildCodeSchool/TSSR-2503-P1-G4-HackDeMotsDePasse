## Sommaire

1. [Prérequis technique](#prerequis-technique)
2. [Installation sur le serveur](#installation-sur-le-serveur)
3. [Installation sur le client](#installation-sur-le-client)
4. [FAQ](#faq)

# 1. Prérequis techniques
<span id="prerequis-techniques"></span>

Pour ce projet, nous avons besoin de deux VM :
- Une VM serveur Windows 2022 : **SERVWIN01**
- Une VM clien Ubuntu : **UBU01**

Nous devons ensuite les mettre en réseau. Pour ce faire nous allons rajouter à chacune une deuxième carte réseau en "réseau interne" avec le même nom, ici "intnet".

Une fois cela fait nous allons configurer l'adresse ip de SERVWIN01 de la deuxième carte réseau avec cette adresse : **172.16.10.5**

Nous configurons également l'ip de UBU01 de "intnet" avec cette adresse ip : **172.16.10.10**

# 2. Installation sur le serveur
<span id="installation-sur-le-serveur"></span>

Sur SERVWIN01, nous allons commencer par télecharger le logiciel **7zip**. Nous le téléchargeons via ce lien : _https://www.7-zip.org/_ et l'installons sur la machine.

Nous pouvons maintenant compresser des fichiers et les encrypter. 

Nous allons créer deux fichiers : _secret_defense1.txt_ et _secret_defense2.txt_ dans le repertoire C://.

Puis nous allons les compresser et les encrypter avec 7zip : 

- Clique droit sur le fichier puis choisir _"add to archive"_
- Ne rien modifier des différentes options
- Choisir le mot de passe dans la case correspondant. Ici nous allons choisir **Defcon2**
- Cocher la case "encrypte file name"
 
Les fichiers sont maintenant encrypter grace à 7zip sur SERVWIN01.


# 3. Installation sur le client
<span id="installation-sur-le-client"></span>

Pour la machine client UBU01, nous avons besoin d'installer le logiciel _John_the_ripper_

Via le terminal nous allons utiliser les commandes suivantes:

    sudo snap install john-the-ripper

Installation John-the-ripper

Ensuite nous allons chercher l'endroit où se situe notre logiciel et nous y rendre

    which john-the-ripper (d'autres touches comme "find" ... sont possibles)

Which John-the-ripper

Se déplacer dans le dossier bin

    cd /snap/bin

et pour découvrir l'ensemble du contenu nous ferons

    ls

et nous trouverons tous les modules john-the-ripper installés.

Trouver John-the-ripper

Pour activer celui que nous voulons, nous ferons

    ./john-the-ripper.zip2john

Activer john2zip


### Hashcat

Via le terminal nous allons utiliser la commande suivante pour télécharger le logiciel HashCat: 

    sudo apt install hashcat
       
Cette commande va également installer les configurations système requise (en anglais _requiered dependencies_).

Maintenant nous allons voir pour télecharger la dernière version de notre logiciel en commencant par les outils de developpement :

    sudo apt install -y build-essential git

Ensuite nous allons cloner le Hashcat Git repository : 

    git clone https://github.com/hashcat/hashcat.git

Une fois installé, nous allons nous deplacer dans le dossier hashcat : 

    cd hashcat

Compiler le code présent : 

    make 

Maintenant nous pouvons installer hashcat avec la dernière version :
    
    sudo make install

Pour être sur que nous soyons a jour, nous allons utiliser cette commande : 

    hashcat --version 

![capture écran version hashcat](Ressources/version_hashcat.png)

Félicitation ! Vous avez installer avec succés le logiciel Hashcat. Pour de plus amples informations vous pouvez consulter l'aide en tapant cette commande dans votre terminal : 

    hashcat --help


    

# 4. FAQ
<span id="faq"></span>
