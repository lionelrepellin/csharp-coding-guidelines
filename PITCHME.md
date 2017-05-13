## Bonnes Pratiques de Codage en C\#

---

### Quelques principes de base

- [KISS : Keep It Simple as Stupid](https://fr.wikipedia.org/wiki/Principe_KISS)

- [DRY : Don't Repeat Yourself](https://fr.wikipedia.org/wiki/Ne_vous_r%C3%A9p%C3%A9tez_pas)

- [YAGNI : You Ain't Gonna Need It](https://fr.wikipedia.org/wiki/YAGNI)

- [Principes SOLID](https://www.exceptionnotfound.net/tag/solid-principles/)

- [Loi de Déméter](https://fr.wikipedia.org/wiki/Loi_de_D%C3%A9m%C3%A9ter)

---

### La règle du boy-scout

*Laissez le campement plus propre que vous ne l'avez trouvé en arrivant.*

---

### Quelques règles générales :

- Un fichier par classe, interface ou énum
- Un namespace par fonctionnalité
- Eviter la notation hongroise
- Eviter les abréviations 
- Switch : penser polymorphisme

+++

### Quelques règles générales :

- Pas de : out, ref, goto, continue, implicit, unsafe *(cf. mots clés interdits)*
- Créer des exceptions personnalisées
- Jamais de catch vide !
- Les propriétés reflètent l'état d'un objet (pas de logique métier !)

---

### Les classes

- Moins de 1000 lignes
- Toujours privilégier du code non statique : 
  - testable / mockable
  - comportement polymorphe : penser objet !
  - héritage technique possible
  - design pattern
- Responsabilité unique *(principe SOLID)*
- Pas de nom de classe fourre-tout : Common, Global...

---

### Les méthodes

- Un nom explicite
- S'occupe d'une et une seule chose
- Un seul return
- Courtes : entre 50 et 100 lignes max
- 3 paramètres distincts maximum *(idéalement zéro)* : 
  - au-delà, passer un objet
  - penser aux tests !

+++

### Les méthodes

- Pas de booléen en argument qui modifie le comportement
- Ne pas passer *null* et ne pas renvoyer *null*
- Pas de logique métier dans les méthodes d'extension : créer un service

--- 

### Les tests

- Ce qui s'applique au code de production, s'applique aux tests !
- Penser aux tests dès la phase de développement
- Les tests doivent être rapides à coder et à s'exécuter
- Un seul concept et un seul Assert par test
- Le projet de tests reflète l'arborescence du projet testé

---

### Les commentaires

- Documenter un fonctionnement un peu *touchy*

- Les commentaires se doivent d'être utiles et non utilisés systématiquement pour commenter chaque étape de son code

---

### La mise en forme

- L'indentation *(espaces ou tabulation)* doit être définit en amont

- Mise en forme horizontale : la barre de scoll horizontale ne devrait pas apparaître dans votre IDE

- Mise en forme verticale : pensez à ce que vous voyez - dans l'ordre - lorsque vous rentrez dans votre voiture :

+++

### La mise en forme verticale

  - la voiture a quatre roues, elle est de couleur rouge : les propriétés publiques
```csharp
    public int WheelsCount { get; set; }
    public string Color { get; set; }
```

  - on rentre dans l'habitacle, il y a un GPS : les champs privés (non visible de l'extérieur) :
```csharp  
    private bool _hasGps = true;
```

+++

### La mise en forme verticale

  - on met le contact, c'est le constructeur ! ;)

  - le véhicule peut avancer, reculer, tourner à gauche et à droite : les méthodes publiques
```csharp  
    public void GoForward();
    public void GoBackward();
    public void TurnLeft();
    public void TurnRight();
```

+++

### La mise en forme verticale

  - on allume l'auto-radio ou l'allume-cigare : les méthodes privées
```csharp
    private void TrunOnTheRadio();
    private void TurnOnTheCigaretteLighter();
```

---

### Les conventions de nommage

- Les interfaces : toujours précédées par « I »
  - IProduct, IProvider, ISurvey

- Les classes : jamais suffixées par « Class » 

- Les enum : jamais suffixées par « Enum »
```csharp
    enum Status { Bad, Medium, Good }
```

---

### Les conventions de nommage

- Champs / variables de classe privées :
```csharp
    private int _myVar;
```

- Propriétés publiques : 
```csharp
    public MyProperty { get; set; }
```

+++

### Les conventions de nommage

- Les constantes de méthode
```csharp
    const string Discriminator = "abc";
```

- Les constantes de classe
```csharp
    public const int MyConst = 123;
```

- Les variables à l'intérieur des méthodes
```csharp
    var myVar = "abc";
```

+++

### Les conventions de nommage

- **this** sert à identifier les propriétés / méthodes héritées ; il n'est pas utile de le faire précéder chaque appel de propriétés / méthodes de la classe courante.

- Utiliser les **alias** (string, int, bool, object au lieu de String, Int32, Boolean, Object…)

---

### Les outils

Move Class to File
  - https://github.com/filipw/Strathweb.Roslyn

SonarLint for Visual Studio
  - http://www.sonarlint.org/visualstudio/index.html

SonarQube
  - https://www.sonarqube.org/

---

### Pour aller plus loin...

31 Days of Refactoring
  - https://lostechies.com/wp-content/uploads/2011/03/31DaysRefactoring.pdf

  - https://lostechies.com/seanchambers/2009/07/31/31-days-of-refactoring/

---

### Références

Coder Proprement de Robert C.Martin (2009)
  - https://www.amazon.fr/Coder-proprement-Robert-C-Martin/dp/2744023272

C# Coding Guidelines
  - https://github.com/dennisdoomen/CSharpGuidelines/releases
  - http://www.dofactory.com/reference/csharp-coding-standards

Mots clés interdits
  - http://www.codethinked.com/ten-c-keywords-that-you-shouldne28099t-be-using
  - http://stackoverflow.com/questions/31859016/is-the-use-of-dynamic-considered-a-bad-practice

---

# Keep Calm and Write Good Code !