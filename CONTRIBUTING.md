# Guide de Contribution - DonguiMemo

## 🚀 Bienvenue Contribuer à DonguiMemo !

Nous sommes ravis que vous souhaitiez contribuer à DonguiMemo ! Ce guide vous aidera à commencer rapidement.

---

## 📋 Sommaire

- [💻 Configuration de Développement](#-configuration-de-développement)
- [🏃‍♂️ Processus de Contribution](#-processus-de-contribution)
- [🐛 Rapports de Bugs](#-rapports-de-bugs)
- [💡 Suggestions de Fonctionnalités](#-suggestions-de-fonctionnalités)
- [🎨 Standards de Code](#-standards-de-code)
- [🧪 Tests](#-tests)
- [📚 Documentation](#-documentation)
- [❓ Questions & Support](#-questions--support)

---

## 💻 Configuration de Développement

### Prérequis
- **Android Studio** 4.0 ou plus récent
- **SDK Android** API 29 (minimum)
- **Git** pour le contrôle de version
- **Java 8** ou **Kotlin** (notre langage principal)

### Installation
```bash
# Clonez le repository
git clone https://github.com/mileverse-studio/DonguiMemo.git
cd DonguiMemo

# Ouvrez le projet dans Android Studio
# Attendez la synchronisation Gradle
# Compilez et testez
```

### Configuration Environnement
1. **Android Studio** : Import du projet
2. **Gradle Sync** : Synchronisation automatique
3. **SDK Setup** : API 21-29 configurés
4. **Emulator/Device** : Test de l'application

---

## 🏃‍♂️ Processus de Contribution

### Workflow Standard
1. **Fork** le repository
2. **Clone** votre fork localement
3. **Créez** une branche feature
4. **Développez** et testez
5. **Committez** avec des messages clairs
6. **Push** vers votre fork
7. **Créez** une Pull Request

### Branches Naming
```
feature/nom-de-la-fonctionnalité
fix/correction-du-bug
improvement/amélioration-existante
docs/mise-a-jour-documentation
```

### Messages de Commit
Utilisez la convention Conventional Commits :
```bash
feat: ajouter système de notifications
fix: corriger crash sur ouverture des habitudes
docs: mettre à jour README avec nouveaux screenshots
style: améliorer indentation du code
refactor: optimiser requête base de données
```

---

## 🐛 Rapports de Bugs

### Template de Rapport
Utilisez ce template pour les bugs :

```markdown
## 🐛 Description du Bug
Description claire et concise du problème.

## 📱 Environnement
- **App Version :** [ex: 1.0.0]
- **Android Version :** [ex: 12]
- **Device :** [ex: Samsung Galaxy S21]

## 🔄 Étapes pour Reproduire
1. Ouvrir l'app
2. Cliquer sur 'Habitudes'
3. Créer une nouvelle habitude
4. Bug se produit

## ✅ Comportement Attendu
Ce qui devrait se passer normalement.

## 📸 Screenshots/Vidéos
Ajoutez des captures d'écran si pertinent.

## 🌍 Additional Context
Toutes autres informations utiles.
```

### Où Signaler les Bugs
- **GitHub Issues** : [github.com/mileverse-studio/DonguiMemo/issues](https://github.com/mileverse-studio/DonguiMemo/issues)
- **Email** : mileverse61@gmail.com
- **Priorité** : Bugs critiques d'abord

---

## 💡 Suggestions de Fonctionnalités

### Template de Suggestion
```markdown
## 💡 Suggestion de Fonctionnalité
Titre descriptif de la fonctionnalité.

## 🎯 Problème Résolu
Quel problème cette fonctionnalité résoudrait-elle ?

## 💭 Solution Proposée
Description de la solution envisagée.

## 🎨 Mockups/Wireframes
Ajoutez des croquis si possible.

## 📊 Impact Estimé
- **Utilisateurs受益és :** [Nombre]
- **Complexité :** Faible/Moyenne/Élevée
- **Priorité :** Haute/Moyenne/Basse

## 🔄 Alternatives Considérées
Autres solutions envisagées.
```

### Processus d'Évaluation
1. **Analyse** de l'impact utilisateur
2. **Évaluation** de la complexité technique
3. **Priorisation** avec la roadmap
4. **Discussion** communautaire
5. **Décision** et planification

---

## 🎨 Standards de Code

### Langages Principaux
- **Kotlin** pour le développement Android
- **XML** pour les layouts
- **SQL** pour Room Database

### Architecture
```
app/
├── src/
│   ├── main/
│   │   ├── java/com/donguimemo/
│   │   │   ├── ui/          # Interface utilisateur
│   │   │   ├── data/        # Accès données
│   │   │   ├── domain/      # Logique métier
│   │   │   └── utils/       # Utilitaires
│   │   ├── res/             # Ressources
│   │   └── AndroidManifest.xml
│   └── test/                # Tests unitaires
└── build.gradle
```

### Conventions de Nom
- **Classes** : PascalCase (ex: `HabitActivity`)
- **Méthodes** : camelCase (ex: `createNewHabit()`)
- **Variables** : camelCase (ex: `userName`)
- **Constantes** : UPPER_SNAKE_CASE (ex: `MAX_HABITS`)
- **XML IDs** : snake_case (ex: `btn_save_habit`)

### Code Style
```kotlin
// Bonne pratique
class HabitManager {
    private val habits = mutableListOf<Habit>()
    
    fun addHabit(habit: Habit) {
        if (habit.name.isNotBlank()) {
            habits.add(habit)
        }
    }
}

// Évitez les longues méthodes
// Documentez les fonctions complexes
// Utilisez des noms explicites
```

---

## 🧪 Tests

### Types de Tests
1. **Unit Tests** : Logique métier
2. **Integration Tests** : Interactions entre composants
3. **UI Tests** : Interface utilisateur avec Espresso
4. **Performance Tests** : Optimisation et performance

### Exemple de Test Unitaire
```kotlin
@Test
fun addHabit_shouldAddToList() {
    // Given
    val habitManager = HabitManager()
    val testHabit = Habit("Read daily")
    
    // When
    habitManager.addHabit(testHabit)
    
    // Then
    assertEquals(1, habitManager.habits.size)
    assertEquals("Read daily", habitManager.habits[0].name)
}
```

### Lancer les Tests
```bash
# Tests unitaires
./gradlew test

# Tests d'instrumentation
./gradlew connectedAndroidTest

# Rapport de couverture
./gradlew jacocoTestReport
```

---

## 📚 Documentation

### Types de Documentation
- **README.md** : Vue d'ensemble du projet
- **API Documentation** : Documentation du code
- **User Guides** : Guides utilisateur
- **Developer Guides** : Guides développement

### Documentation du Code
```kotlin
/**
 * Gère les opérations liées aux habitudes utilisateur.
 * 
 * @param habitRepository Repository pour l'accès aux données
 * @since 1.0.0
 */
class HabitManager(
    private val habitRepository: HabitRepository
) {
    /**
     * Ajoute une nouvelle habitude à la liste.
     * 
     * @param habit L'habitude à ajouter
     * @throws IllegalArgumentException si le nom est vide
     */
    fun addHabit(habit: Habit) {
        require(habit.name.isNotBlank()) {
            "Le nom de l'habitude ne peut pas être vide"
        }
        habitRepository.save(habit)
    }
}
```

### Guides Utilisateur
Création de guides pour :
- Démarrage rapide
- Gestion d'habitudes avancée
- Utilisation des flashcards
- Organisation des notes

---

## 🌍 Internationalisation

### Langues Supportées
- **Français** (par défaut)
- **Anglais**
- Autres langues en cours

### Ajout de Traductions
1. **Créez** les fichiers dans `values-[locale]/strings.xml`
2. **Traduisez** les textes
3. **Testez** dans l'application
4. **Mettez à jour** la documentation

---

## 🔍 Processus de Revue

### Review Checklist
- [ ] **Code Quality** : Standards respectés
- [ ] **Tests** : Tests ajoutés/mis à jour
- [ ] **Documentation** : Commentaires et docs
- [ ] **Performance** : Pas de régressions
- [ ] **Sécurité** : Pas de vulnérabilités
- [ ] **Accessibilité** : Conformité a11y

### Timeline de Revue
- **Révision initiale** : 24-48h
- **Demandes de changements** : 3-5 jours
- **Révision finale** : 24h
- **Merge** : Après approbation complète

---

## 🏆 Reconnaissance

### Hall of Fame
Contributors notables seront listés dans :
- **README.md** principal
- **Release Notes** de chaque version
- **GitHub Contributors** page

### Types de Contributions Reconnues
- 🐛 **Bug fixes**
- 💡 **Nouvelles fonctionnalités**
- 📚 **Améliorations documentation**
- 🎨 **Améliorations UI/UX**
- 🧪 **Tests et qualité**

---

## 📞 Support & Questions

### Channels de Support
- **GitHub Discussions** : Questions générales
- **GitHub Issues** : Bugs et fonctionnalités
- **Email** : mileverse61@gmail.com
- **YouTube** : Tutoriels et démonstrations

### Communauté
Rejoignez notre communauté en ligne :
- **YouTube** : [youtube.com/@donguimemo](https://youtube.com/@donguimemo?si=vchZ-Z384-EE3bIV)
- **Support Email** : donguimemo.app@gmail.com

---

## 🎯 Roadmap & Priorités

### Priorités Actuelles
1. **Stabilité** - Bugs critiques
2. **Performance** - Optimisation
3. **UX** - Interface utilisateur
4. **Nouvelles fonctionnalités** - Roadmap
5. **Documentation** - Guides et tutoriels

### Comment Prioriser
Contributeurs peuvent influencer la roadmap via :
- **Upvotes** sur les issues
- **Suggestions** dans les discussions
- **Participation** aux décisions

---

## 📋 Checklist Finale

Avant de soumettre une contribution :

- [ ] **Code testé** sur device réel
- [ ] **Standards de code** respectés
- [ ] **Tests ajoutés** si nécessaire
- [ ] **Documentation** mise à jour
- [ ] **Messages de commit** clairs
- [ ] **Pull Request** bien décrite
- [ ] **Screenshots/vidéos** incluses si applicable

---

## 🙏 Merci !

Chaque contribution, grande ou petite, aide à améliorer DonguiMemo pour tous les utilisateurs.

**Nous avons hâte de voir vos contributions !**

---

**Développé avec ❤️ par MileVerse Studio**  
**Dernière mise à jour : 20 novembre 2025**