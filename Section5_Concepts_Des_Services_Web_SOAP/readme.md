<center><h1><u>Concepts Des Services Web SOAP</u></h1></center>

| Lecture                                          |
|--------------------------------------------------|
| Introduction                                     |
| Présentation des services Web SOAP               |
| Avantages et inconvénients des services Web SOAP |
| Quand utiliser les Web Services SOAP ?           |
| SOAP                                             |
| Explication du fichier WSDL                      |
| Styles de liaison WSDL                           |
| Résumé de la section                             |


<center><h2><u>Introduction</u></h2></center>

+ **Les conférences de cette section sont essentielles pour vous permettre de comprendre `quoi, pourquoi et quand utiliser les services Web SOAP dans vos applications`.**
+ **À la fin, vous découvrirez les différents `avantages et inconvénients des services Web Soap` ainsi que `les éléments constitutifs des services Web Soap`, à savoir `SOAP, WSDL et HTTP`.** 
+ **Vous en parlerez en maîtrisant les différentes sections d'un `fichier WSDL`.**


<center><h1><u>Présentation des services Web SOAP :</u></h1></center>

+ **Ce serait vraiment génial si toutes les applications logicielles de cette planète pouvaient communiquer entre elles et s'utiliser les unes les autres, quel que soit le langage dans lequel elles sont développées et la plate-forme ou le système d'exploitation sur lequel elles s'exécutent. La promesse des services Web cette merveille et tenir cette promesse.**

<br/>

+ **Ils ont permis `une communication facile et faiblement couplée` entre des applications exécutées sur différents systèmes d'exploitation construits à l'aide de différents langages de programmation.**

<br/>

+ **`Les services Web` sont au monde du logiciel ce que `l'anglais est à cette planète`. `Ils constituent un terrain d'entente ou un langage permettant de communiquer entre des applications logicielles exécutées sur différentes plates-formes`.**

<br/>

+ **Lorsque vous regardez cette vidéo, vous accédez à une application Web, dans laquelle ce `site Web est le fournisseur de services Web` et vous via votre navigateur comme `Internet Explorer, Chrome ou Firefox ou Safari`. Vous êtes `le consommateur du service`.**

<br/>

+ **`Les applications Web` fonctionnent` en http et en HTML`, tandis que `les services Web` fonctionnent `en http et en XML`, tandis que le HTML n'est compris que par le navigateur Web et utilisé pour la présentation.**

<br/>

+ **`XML` peut être lu par n'importe quelle application logicielle et le convertir en objets langage dans lesquels cette application a été écrite.**

<br/>

+ **Nos applications peuvent être des `fournisseurs de services Web ou des consommateurs de services Web`, ou les deux.**

<br/>

+ **Voici le scénario dans lequel une application `.NET` exécutée dans l'environnement `Windows` communique avec cette application `Java` exécutée dans l'environnement `Linux`. Via `des messages HTTP et Soap au format XML`.**

<br/>

+ **Cette application `Java` communique à son tour avec une `application Web mainframe` héritée via des services Web. Un monde rempli de services qui peuvent s’utiliser les uns les autres quand et où cela est nécessaire. La puissance du XML vient de ses données et métadonnées. Comme vous pouvez le voir ici, ici les données sont `bharath` qui est le nom du client.**

<br/>

+ **Et puis `les métadonnées sont en fait l'élément nom du client`. Toute plate-forme ou langage lisant ce XML sait ce que ces données signifient. C'est le nom du client. Il peut donc être facilement converti en un objet langage et les valeurs peuvent lui être attribuées afin que notre L'application peut faire quelque chose avec ces données dans le `xmlè . Les services Web peuvent se trouver au sein d'une seule entreprise ou organisation ou n'importe où sur Internet et nos applications communiquent parfois avec les services Web de cette entreprise ou organisation.**

<br/>

+ **Parfois, ils peuvent accéder à des services Web extérieurs à l'organisation, n'importe où sur Internet. Pour conclure, ceci avec un exemple en temps réel.**

<br/>

+ **Voici un logiciel de gestion hospitalière qui se décompose en composants ou services.**

<br/>

+ **Nous avons `les services aux patients` qui traiteront toutes `les informations sur le patient`, comme la date de son enregistrement, puis quelles sont ses informations d'assurance et tout ça.**

<br/>

+ **Ensuite, `les services cliniques` qui géreront toutes `les informations cliniques liées au patient`, comme les informations sur les tests sanguins, les radiographies, etc. a = Et puis nous avons les services de facturation qui factureront le patient une fois qu'il aura terminé tous les services et l'hôpital. il a vérifié ou tout au long de ce processus.**

<br/>

+ **Ce sont donc les trois composants importants du système de gestion hospitalière qui `communiquent entre eux via des services Web de manière très faiblement couplée`, uniquement lorsque cela est nécessaire et là où cela est nécessaire.**

<br/>

+ **Ensuite, nous avons `les services d'assurance qui sont en dehors de l'hôpital et les services de facturation` peuvent faire appel aux services d'assurance en utilisant les informations du patient, le patient fournit quelle assurance il a. Et en fonction de cela, les services de facturation vérifient également les services cliniques dont il bénéficie. Je suis allé et après avoir rassemblé toutes ces informations, les gens appellent le service d'assurance particulier qui se trouve à l'extérieur de l'hôpital pour facturer la compagnie d'assurance et obtenir tout l'argent que l'hôpital devrait recevoir.**

<br/>

+ **`Grâce aux services Web, tous ces composants communiquent de manière transparente`.**

<br/>

+ Pour résumer cette conférence, vous avez appris ce que sont les services Web et comment `ils permettent une communication transparente entre les applications exécutées sur différentes plates-formes`.**

<br/>

+ **Nous devons retenir une chose à propos des services Web de cette conférence : c'est ce que l'anglais représente pour cette planète pour l'industrie du logiciel.**

<br/>

+ **Ils constituent un terrain d’entente pour communiquer entre des applications logicielles exécutées sur différentes plates-formes et langages.**


# **Quizz : SOAP Web Services Overview**



#### **Question 1 :**
+ Lors de l'utilisation des `services Web SOAP`, quels types de données est envoyé via le protocole `HTTP`?
    + `XML`

#### **Question 2 :**
+ Les deux types d'application ou de composants dans les `services Web et SOA` sont?
    + `fournisseur et consommateur`

#### **Question 3 :**
+ La puissance de `XML` vient de ses `métadonnées` et ?
    + `données`

