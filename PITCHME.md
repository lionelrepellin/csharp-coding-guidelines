# Bonnes Pratiques de codage en C#

---

# Quelques principes de base

### KISS : https://fr.wikipedia.org/wiki/Principe_KISS

### DRY : https://fr.wikipedia.org/wiki/Ne_vous_r%C3%A9p%C3%A9tez_pas

### YAGNI : https://fr.wikipedia.org/wiki/YAGNI

### SOLID : https://www.exceptionnotfound.net/tag/solid-principles/

### Loi de Déméter : https://fr.wikipedia.org/wiki/Loi_de_D%C3%A9m%C3%A9ter

---

# Coder Proprement
## La règle du boy-scout

*Laissez le campement plus propre que vous ne l’avez trouvé en arrivant.*

---

# Coder Proprement
## Quelques règles générales :

- Un fichier par classe, interface ou énum
- Un namespace par fonctionnalité
- Eviter la notation hongroise
- Eviter les abréviations 
- Switch : penser polymorphisme
- Pas de : out, ref, goto, continue, implicit, unsafe (cf. mots clés interdits)
- Créer des exceptions personnalisées
- Jamais de catch vide !
- Pas de logique métier dans les propriétés : elles reflètent l’état d’un objet

---

# Coder Proprement
## Les classes

- Moins de 1000 lignes
- Toujours privilégier du code non static : 
  - testable / mockable
  - comportement polymorphe
  - héritage technique possible
  - design pattern
  - penser objet !
- Responsabilité unique (principe SOLID)
- Pas de nom de classe fourre-tout : Common, Global, etc.

---

# Coder Proprement
## Les méthodes

- Un nom explicite
- S'occupe d’une et une seule chose
- Un seul return
- Courtes : entre 50 et 100 lignes max (on ne décrypte pas, on lit !)
- 3 paramètres distincts maximum (idéalement zéro) : 
  - au-delà, passer un objet
  - penser aux tests !
- Pas de booléen en argument qui modifie le comportement
- Ne pas passer *null* et ne pas renvoyer *null*
- Pas de logique métier dans les méthodes d’extension : créer un service

--- 

# Coder Proprement
## Les tests

- Ce qui s'applique au code de production, s'applique aux tests !
- Penser aux tests dès la phase de développement
- Les tests doivent être rapides à coder et à s’exécuter
- Un seul concept et un seul Assert par test
- Le projet de tests reflète l'arborescence du projet testé

---

# Coder Proprement
## Les commentaires

- Documenter un fonctionnement un peu touchy
- Les commentaires se doivent d'être utiles et non utiliser systématiquement pour commenter chaque étape de son code

---

# Coder Proprement
## La mise en forme

- L'indentation (espaces ou tabulation) doit être définit en amont
- Mise en forme horizontale : la barre de scoll horizontale ne devrait pas apparaître dans votre IDE
- Mise en forme verticale : pensez à ce que vous voyez - dans l'ordre - lorsque vous rentrez dans votre voiture :
  - la voiture a quatre roues, elle est de couleur rouge : les propriétés publiques
```csharp
    public int WheelCount { get; set; }
    public string Color { get; set; }
```
  - on rentre dans l'habitable, il y a un GPS : les champs privés (non visible de l'extérieur) :
```csharp  
    private bool _hasGps = true;
```
  - on met le contact, c'est le constructeur
  - le véhicule peut avancer, reculer, tourner à gauche et à droite : les méthodes publiques
```csharp  
    public void GoForward();
    public void GoBackward();
    public void TurnLeft();
    public void TurnRight();
```
  - on allume l'autoradio ou l'allume-cigare : méthodes privées
```csharp  
    private void TrunOnTheRadio();
    private void TurnOnTheCigaretteLighter();
```

---

# Best Practices
## Les conventions de nommage

- Les interfaces : toujours précédées par « I »
  - IProduct, IProvider, ISurvey

- Les classes : jamais suffixées par « Class » 

- Les enum : jamais suffixées par « Enum »
  - exemple : enum Status { Bad, Medium, Good }

- Interfaces, classes et enum : PascalCase

---

# Best Practices
## Les conventions de nommage

- Champs / variables de classe private : _myVar
- Propriétés public : MyProperty { get; set; }
- Constantes : MyConst
- Variable de méthode : myVar
- this sert uniquement à identifier les propriétés / méthodes héritées
- Utiliser les alias (string, int, bool, object au lieu de String, Int32, Boolean, Object…)

---

# Les outils

### Move Class to File
  - https://github.com/filipw/Strathweb.Roslyn

### SonarLint for Visual Studio
  - http://www.sonarlint.org/visualstudio/index.html

### SonarQube
  - https://www.sonarqube.org/

---

# Pour aller plus loin…

### 31 Days of Refactoring
  - https://lostechies.com/wp-content/uploads/2011/03/31DaysRefactoring.pdf
  - https://lostechies.com/seanchambers/2009/07/31/31-days-of-refactoring/

---

# Références

### C# Coding Guidelines
  - https://github.com/dennisdoomen/CSharpGuidelines/releases
  - http://www.dofactory.com/reference/csharp-coding-standards

### Coder Proprement

### Mots clés interdits
  - http://www.codethinked.com/ten-c-keywords-that-you-shouldne28099t-be-using
  - http://stackoverflow.com/questions/31859016/is-the-use-of-dynamic-considered-a-bad-practice

---

# Keep Calm And Write Good Code

---