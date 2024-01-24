<center><h1><u>XML et définition de schéma XML et JSON</u></h1></center>





<center>

| Lecture                                        |
|------------------------------------------------|
| Presentation                                   |
| Qu'est-ce que XML ?                            |
| Pourquoi XML ?                                 |
| Quand utiliser XML ?-                          
| Qu'est-ce que XSD ?                            |
| Quand utiliser XSD ?                           |
| Espaces de noms                                |
| Cas d'utilisation pratique du schéma XML       |
| Pratique du schéma XML                         |
| Création de types simples-                     
| Contrôler l'ordre des éléments                 |
| Contrôler le nombre d'éléments                 |
| Signification de l'attribut elementFormDefault |
| Définir les attributs                          |
| Résumé de la section                           |
| Introduction à JSON                            |
| JSON pratique                                  |
| Analyse JSON                                   |

</center>

<center><h1><u>Introduction</u></h1></center>

+ **`XML` est principalement utilisé à deux endroits dans les applications logicielles : `un comme fichier de configuration et deux pour l'échange de données`.**

<br/>

+ **Vous utiliserez `XML` à ces deux fins tout au long du cours sur `les services Web`.**

<br/>

+ **`Apache CXF`, le moteur de services Web utilise `la configuration Spring qui est XML` et `les services Web SOAP et les services Web REST échangent des données au format XML`.**

<br/>

+ **Vous commencerez par maîtriser comment `créer un document XML`, ce qu'est la bonne formation, puis vous apprendrez à définir le contrat pour un document `XML`.**

<br/>

+ **Étant donné que `XML` est utilisé par plusieurs parties, `le fournisseur du service Web et le consommateur du service Web`, nous devons définir un contrat pour le `XML`. Nous le faisons en utilisant `les éléments de la définition du schéma XML`.**

<br/>

+ **Enfin, vous terminerez en apprenant ce que sont les espaces de noms. Les espaces de noms nous permettent de qualifier de manière unique un élément `XML`, ce qui nous permet d'utiliser plusieurs éléments portant le même nom dans un document `XML`.**

<br/>

+ **Commençons donc par examiner ce qu’est `XML` et pourquoi est-il si puissant.**


<center><h1><u>Qu'est-ce que XML ?</u></h1></center>

+ **À partir de cette conférence, vous apprendrez ce qu'est `XML` ? `XML` signifie `Extensible Markup Language`, car son nom lui-même indique que nous pouvons créer notre propre balisage requis pour nos objectifs commerciaux en utilisant `XML`.**

<br/>

+ **Si vous êtes familier avec le `HTML`, vous savez que le `HTML` fournit un ensemble prédéfini d'éléments qui ajoutent une signification particulière aux données qu'ils enveloppent.**

<br/>

+ **Par exemple `<b>John</b>` ici en gras entouré des balises `'b'` les balises `html` seront interprétées par les navigateurs web comme `Internet Explorer Chrome et Firefox en gras H1 affichera ce texte ici`. Bienvenue dans le monde de `XML`. Dans une police légèrement plus grande et en gras.**

<br/>

+ **Ainsi, `HTML` ajoute une signification particulière aux données ou ajoute une valeur de présentation aux données qu'il enveloppe et il possède un ensemble d'éléments prédéfinis alors que `XML` n'a aucun ensemble d'éléments prédéfinis.**

<br/>

+ **Cela nous permet de créer notre propre `XML en utilisant XML`. Nous pouvons définir notre propre balisage. Par exemple, si nous travaillons sur une application de commerce électronique, nous pouvons créer une commande qui aura l'identifiant de la commande, les éléments de ligne, l'adresse de livraison et tout ce dont nous avons besoin. pour les données de commande.**

<br/>

+ **De même, si nous travaillons sur un portail d'actualités, nous pouvons créer un NewsML qui peut faire la une des journaux. Informations politiques et informations politiques ou actualités politiques ainsi que données sportives. Les applications peuvent ensuite utiliser ce `XML` pour le sauvegarder afin de le manipuler et de l'afficher à l'utilisateur final ou même d'échanger ces informations avec d'autres applications, c'est toute la puissance du `XML`.**

<br/>

+ **Pour résumer, `XML signifie Extensible Markup Language`. Contrairement au HTML, `il n'a aucun ensemble d'éléments prédéfinis`. Cela nous permet de créer notre propre langage de balisage ou des éléments de balisage afin que nos applications puissent utiliser les données comme elles le souhaitent et qu'elles puissent faire ce qu'elles veulent avec ces données très facilement.**



<center><h1><u>Pourquoi XML ?</u></h1></center>


+ **`Pourquoi XML ou quels sont les avantages de XML ?` L'avantage numéro un que vous connaissez déjà lors de la conférence précédente est que nous pouvons créer notre propre balisage personnalisé en utilisant `XML`. Par exemple, si nous travaillons sur une application de commerce électronique, nous pouvons créer un fichier `XML de commande` contenant l'identifiant de la commande, les informations d'expédition sur toutes les informations sur le produit, etc.**

<br/>

+ **Le deuxième et principal avantage du `XML` est qu'il `transporte à la fois les données et les métadonnées`. Par exemple, disons que nous travaillons tous ensemble pour Amazon sur leur application Web Amazon qui permet aux clients de passer une commande puis d'effectuer une expédition Amazon. application qui expédiera la commande pour le client lorsqu'elle sera prête.**

<br/>

+ **Désormais, dès que le client passe une commande ou lorsque le produit est prêt à être expédié, l'application Web Amazon envoie les données à l'application d'expédition Amazon au format `XML`. L'application d'expédition Amazon qui regarde ce fichier XML qui contient à la fois les données 123 pour l'ID de commande et notre adresse pour les informations d'expédition et les métadonnées qui sont l'ID de commande, les informations d'expédition savent quoi faire avec ces données, savent immédiatement qu'il s'agit d'une commande. 123 et les informations d'expédition correspondent à l'endroit où la commande doit être expédiée.**

<br/>

+ **Enfin, `XML` suit certaines règles de bonne forme. Nous devons donc nous assurer que les applications qui produisent du `XML` doivent s'assurer qu'elles envoient un `XML` propre, sinon les applications qui traitent le `XML` peuvent le rejeter.**

<br/>

+ **De même, nous avons des `règles de validation` qui sont très puissantes. Nous pouvons créer des fichiers de schéma pour notre `XML`. Et puis ces applications qui échangent des données. Par exemple, lorsque l'application Web Amazon envoie les données, l'application d'expédition peut valider ces données par rapport à un schéma sur lequel ils ont accepté avant même le développement de ces applications.**

<br/>

+ **Pour résumer, les principaux avantages de l'utilisation de `XML` sont qu'il nous permet de `créer un balisage personnalisé`. Il contient à la fois des `métadonnées et des données`, ce qui permet aux applications de consommer facilement les données et d'en tirer un sens. suit certaines règles de bonne formation et cela nous permet également de valider les données avant de faire quoi que ce soit avec ces données.**


<center><h1><u>Quand utiliser XML ?</u></h1></center>

+ **Il y a trois endroits dans lesquels est principalement utilisé ou devrait être utilisé**

  + **Pour l'échange de données**
  + **Pour les fichiers de configuration**
  + **Sauvegarder les données, manipuler et présenter les données.**


+ **Pour l'échange de données, par exemple, nous avons l'application 1 et l'application 2 et ces deux applications montrent comment certaines données sont en commun ou elles souhaitent échanger certaines données. `XML` est la voie à suivre car `XML` contient à la fois `des données et des metadonnées` et il peut être également validé.**

+ **Les technologies que nous pouvons utiliser pourraient être `des services Web de SOAP, des services Web REST, RBC ou des appels à distance`, cela n'a pas d'importance. Mais tous ceux-ci utilisent `XML` en interne pour échanger les données.**

+ **Deuxièmement en tant que `fichier de configuration`, si vous êtes développeur de logiciels ou testeur vous connaissez déjà plusieurs fichiers de configuration comme le `web.xml` dans l'espace Java pour les applications `web.Server.xml` pour les serveurs d'applications `le pom.xml et build.xml` pour vos fichiers de construction.**

+ **Ainsi, `XML` peut être facilement utilisé comme `fichiers de configuration` car nous pouvons à nouveau `fournir ces informations de configuration` sous forme de données, puis `les metadata indiquent à quoi servent ces informations de configuration`.**

+ **Enfin, nous pouvons utiliser `XML pour enregistrer les données, les manipuler et les présenter à l'utilisateur`.**

+ **Voici donc les trois grands domaines dans lesquels XML peut être utilisé, depuis l'échange de données jusqu'aux fichiers de configuration, en passant par la sauvegarde des données, leur manipulation et leur présentation au client.**



<center><h1><u>Qu'est-ce que la définition de schéma XML/XSD ?</u></h1></center>

+ **À partir de cette conférence, vous apprendrez ce qu'est `une définition de schéma XML`? Le schéma XML définit la grammaire ou un modèle pour un document XML. c'est-à-dire que nous pouvons utiliser `le schéma XML` pour mentionner quels `éléments` peuvent être présents dans un `XML`. Quels `attributs` peuvent être là, quels espaces de noms `XML` peut utiliser, `l'ordre` dans lequel les éléments doivent apparaître, le nombre d'occurrences de chaque élément et nous pouvons également restreindre les données contenues dans le document XML uniquement à certaines valeurs.**

+ **Tout cela peut être fait en utilisant `la définition de schéma XML`. Si un document `XML` suit le fichier de schéma s'il a un `schéma XML défini` et qu'il suit ce fichier de schéma, il est appelé `un document XML valide`.**

+ **`La définition de schéma XML est également un fichier XML avec une extension point XSD`, au lieu de `.xml`, elle aura un `.xsd` qui signifie `définition de schéma XML`. Tous les éléments que nous pouvons utiliser dans un fichier de schéma sont fournis par le `W3C(World Wide Web Consortium)`.**

+ **Ils définissent la spécification du `schéma XML`. Par exemple, si nous avons un order.xml, nous pouvons avoir un `order.xsd` qui indique quels éléments peuvent être présents et quels attributs peuvent être présents et dans quel ordre dans le `order.xml`.**

+ **Pour résumer, en utilisant un fichier de schéma, nous pouvons définir `la grammaire de nos documents XML`. Un fichier de schéma est également un fichier XML et les éléments pouvant être utilisés dans ce fichier de schéma sont fournis par le `World Wide Web Consortium`.**

+ **Si un document `XML` a un fichier de schéma défini, et s'il suit ce fichier de schéma, cela s'appelle `un document XML valide`.**


<center><h1><u>Quand utiliser la définition de schéma XML</u></h1></center>

**Pourquoi avons-nous besoin d'un fichier de schéma XML et où l'utilisons-nous ?**

<br/>

+ **`Le fichier de schéma XML est un contrat entre deux utilisateurs XML`. C'est-à-dire si l'application 1 et l'application 2 échangent des messages XML pour certaines données sans contrat pour définir quels éléments et attributs doivent être morts dans ce document `XML`, l'application peut envoyer dans toutes les données en `XML` dont l'application deux ne s'en soucie même pas ou ne comprend même pas.**

+ **De même, l'application deux peut également faire quelque chose de similaire en envoyant des données incorrectes ou des données supplémentaires dont l'application ne se soucie pas, c'est là que `la définition du schéma XML` entre en scène.**

+ **Et ces deux applications écrivent lors de leur développement peuvent se mettre d'accord sur un contrat en définissant tous les éléments et attributs à l'intérieur du `fichier de définition de schéma XML pour ce XML`.**

+ **De même, disons que nous avons acheté un nouveau logiciel de gestion des employés pour notre entreprise. Et maintenant, ce logiciel de gestion des employés d'un tiers doit accéder à notre base de données des employés.**

+ **Et ce logiciel tiers nous a demandé d'utiliser un fichier de configuration XML afin que nous indiquions à ce logiciel où se trouve notre base de données et comment y accéder dans ce `fichier de configuration XML`.**

+ **Ce logiciel tiers validera notre fichier XML que nous avons créé par rapport à ce fichier de schéma. Et ils nous fournissent le schéma afin qu'en examinant le fichier de schéma, nous sachions quels éléments nous pouvons inclure dans ce fichier de configuration.**

+ **Ainsi, où et quand vous utilisez XML pour vous assurer que le `XML est valide`, il contient des données valides.**

+  **Nous avons besoin d'un contrat et c'est là que la définition du schéma XML entre en jeu et nous pouvons spécifier tout ce que XML peut avoir dans une `définition de schéma XML`.**


<center><h1><u>Quizz</u></h1></center>

### **Question 1**

+ Le Schema `XML` est un document `XML` ?
    + `VRAI`

### **Question 2**

+ Lequel des éléments en langage `Java` est similaire à un fichier de schema `XML`?
    + `Classe`
        + *Nous pouvons créer plusieurs documents `XML` conformes à un schéma. De même, nous pouvons créer plusieurs objets ou instances de classes.*

### **Question 3**
+ Si un `XML` suit un schéma, il s'appelle `what.xml`.
    + `valide`



<center><h1><u>Espaces de noms/Namespaces</u></h1></center>


+ **À partir de cette conférence, vous apprendrez ce que sont `les espaces de noms` et pourquoi nous en avons besoin. `Les espaces de noms` identifient de manière unique `les éléments et les attributs d'un document XML`.**

<br/>

+ **Lorsque nous créons un fichier de schéma, par exemple, disons que nous travaillons sur la création de fichiers de schéma pour `amazon.com` et `ebay.com` afin de gérer leurs commandes.**

<br/>

+ **La première étape serait lorsque nous définissons un schéma qui attribuera un espace de noms cible pour tous les éléments dans l'ordre d'Amazon en utilisant l'attribut d'espace de noms cible de `la spécification du schéma XML` et nous utiliserons une URL unique d'Amazon.**

<br/>

+ **C'est toujours une bonne pratique d'utiliser une URL de l'entreprise car elle est unique au monde et sur Internet pour un espace de noms.**

<br/>

+ **Et puis, si vous définissez un espace de noms cible pour eBay, il ressemblerait à ceci où il utiliserait le nom de domaine d'eBay ou l'URL d'ebay.**

<br/>

+ **Une fois que nous avons défini un espace de noms cible dans leurs fichiers de schéma respectifs, nous pouvons utiliser un préfixe au lieu d'utiliser cette URL d'entrée pour qualifier chaque élément du schéma `XML et XML`. Plus tard, nous pouvons utiliser un préfixe comme celui-ci.`xmlns` signifie `espace de noms XML`. Cet attribut provient de la spécification XML, quel que soit le `préfixe` que nous souhaitons utiliser.**

<br/>

+ **A partir de ce moment, nous ferons référence à cette URL et nous pourrons alors qualifier tous les éléments en utilisant cet amz au lieu de cette URL entière.**

<br/>

+ **De même, si nous définissons un préfixe pour eBay, voici les deux points `xmlns`. eBay est le préfixe, cela pourrait être $x$, $y$, $z$ ou n'importe quoi.**

<br/>

+ **Et puis l'espace de noms réel. Une fois que nous avons défini l'espace de noms cible et qualifié tous les éléments que nous créons avec ces préfixes lorsque nous créons `le document XML`, ce document doit également utiliser l'espace de noms exact.**

<br/>

+ **Par exemple, la commande pour amazon, l'élément racine de la commande aura le préfixe `xmlns` deux-points défini pour `l'espace de noms et tous les éléments de cet ordre seront qualifiés avec ce préfixe`.**

<br/>

+ **De même, la commande pour eBay utilisera les deux points `XML` d'eBay, puis tous les éléments à l'intérieur seront à nouveau qualifiés avec l'espace de noms d'eBay pour une raison commerciale, si nous devons utiliser plusieurs commandes d'eBay et d'Amazon dans un seul `document XML` en regardant l'espace de noms. Nous savons de quelle entreprise ou si la commande vient d'Amazon ou s'il s'agit d'une commande d'ebay.**

<br/>

+ **Pour résumer `les espaces de noms` nous permettent `d'identifier de manière unique les éléments et les attributs dans un document XML`, nous créons des `espaces de noms cibles` dans le fichier de schéma qui `indiquent que tous les éléments de ce fichier de schéma doivent suivre un certain espace de noms, puis au lieu d'utiliser l'URL entière pour qualifier chaque élément du schéma, nous utilisons un préfixe`.**

<br/>

+ **Si vous êtes issu d'un environnement orienté objet ou programmation, `le monde de l'espace de noms` Java n'est rien d'autre qu'un `package` dans lequel vous créez des classes et les placez dans un certain package et dans le monde `.NET`, cela s'appelle `un espace de noms`, où vous créez des `classes` et les placez dans des `espaces de noms`.**

<br/>

+ **Vous apprendrez plus tard quelques sujets avancés sur les espaces de noms dans les sections. Mais pour l'instant, ces informations sont assez utiles pour vous permettre de démarrer avec la création de schémas XML et vous créerez des espaces de noms cibles en préfixant les éléments de ce fichier de schéma avec ces espaces de noms.**


<center><h1><u>Quizz</u></h1></center>

### **Question 1**
+ Un `XML` ne peut contenir que des éléments d'un `seul espace de noms`.
    + `FAUX`

### **Question 2**
+ Au lieu d'utiliser l'intégralité de l'`URL` de l'`espace de noms` pour faire faire référence à un élément `XML`, nous pouvons utiliser : 

    + `un préfixe`
  
### **Question 3**
+ A quoi sert un espace de noms?
    + `Permet l'utilisation d'élements de différents schémas dans un seul document XML`.



<center><h1><u>Cas d'utilisation pratique du schéma XML</u></h1></center>

+ [PatientXML](../Section4_XML_Et_Definition_De_Schema_XML_JSON/PatientXML)

<center><h1><u>Quizz : Types simples et complexes de schéma XML</u></h1></center>

### **Question 1**

+ Quel est l'élément racine d'un fichier schéma ?

  + `xsd:schema`

### **Question 2**

+ Quel élément du schéma `XML` peut être utilisé pour restreindre les valeurs ?

  + `xsd:restriction`


<center><h1><u>Quizz : Occurrences et ordre des éléments de schéma</u></h1></center>

### **Question 1**

+ Lequel de ces éléments suivants garantit l'ordre dans lequel les éléments `XML` doivent apparaitre ?

  + `xsd:seqeuence`


### **Question 2**

+ Quels sont les deux attributs de schéma qui peuvent être utilisés pour controller le nombre d'occurrences d'éléments dans `XML`?

  + `minOccurs et maxOccurs`


<center><h1><u>Resumé de la section</u></h1></center>
  
<center><img src="images/image7.jpeg"/></center><br/>
<center><img src="images/image8.jpeg"/></center><br/>
<center><img src="images/image9.jpeg"/></center><br/>


<center><u><h1>Pratique-Analyse-JSON</h1></u></center>

+ [JSON Guides](https://www.json.org/json-en.html)

```
// Create a JSON Objects
customerOrder = {
	"customerName": "Etienne", 
  "phoneNumber":789, 
  "items": ["Laptop", "iphone"]
  };

console.log(customerOrder.phoneNumber);

// Serialize the JSON Objects into the string
var jsonString = JSON.stringify(customerOrder);

console.log(jsonString);

// Deserialize JSON string into the Javascript object
var customerOrderDeSerialized = JSON.parse(jsonString);

console.log(customerOrderDeSerialized);
```


<center><u><h1>Memo XML Schema Definition</h1></u></center>

### **1) Élément `<schema>`:**

+ L'élément racine qui contient `l'intégralité de la définition du schéma XML`.
  + Il comprend des attributs tels que : 

    + **targetNamespace**, 
    + **elementFormDefault**, 
    + **attributeFormDefault, etc**.

    ```
    
    <schema
      targetNamespace="namespaceURI"
      elementFormDefault="qualified"
      attributeFormDefault="unqualified">
      <!-- ... -->
    </schema>
    
    ```



### **2) Élément `<element>`:**

+ Définit un élément dans le document XML.
+ Les attributs incluent :

  + **name**, 
  + **type**, 
  + **minOccurs**, 
  + **maxOccurs, etc**.

  ```
  <element name="elementName" type="dataType" minOccurs="0" maxOccurs="unbounded"/>

  ```
  
### **3) Élément `<complexType>` :**

+ Définit la structure des éléments complexes (éléments avec attributs ou éléments imbriqués).
+ Contient : 
  + **des séquences,** 
  + **des choix**
  + **d’autres définitions de contenu complexes.**

  ```
  
  <complexType name="typeName">
    <sequence>
     <!-- ... -->
    </sequence>
   <attribute name="attributeName" type="attributeType"/>
  </complexType>

  ```

### **Élément `<simpleType>`:**

+ Définit la structure des éléments simples (éléments sans attributs ou éléments imbriqués).
+ Spécifie le type de données et les restrictions.

      ```
      <simpleType name="typeName">
        <restriction base="dataType">
        <!-- ... -->
        </restriction>
      </simpleType>
     ```
  
### **Élément `<sequence>`:**

+ Spécifie que les éléments enfants doivent apparaître dans un ordre séquentiel.

    ```
    <sequence>
      <!-- ... -->
    </sequence>
    ```

### **Élément `<choice>`:**

+ Spécifie qu'un seul des éléments enfants doit apparaître.

    ```
    <choice>
      <!-- ... -->
    </choice>
    ```

### **Élément `<attribute>`:**

+ Définit un attribut pour un élément.
+ Les attributs incluent name, type, use(facultatif ou obligatoire), etc.

      <attribute name="attributeName" type="dataType" use="optional"/>

### **Élément `<attributeGroup>`:**

+ Regroupe plusieurs attributs pour les réutiliser.

      <attributeGroup name="groupName">
        <!-- ... -->
      </attributeGroup>

### **Élément `<annotation>`:**

+ Fournit une documentation supplémentaire ou des commentaires pour les éléments.

      <annotation>
        <documentation>...</documentation>
      </annotation>