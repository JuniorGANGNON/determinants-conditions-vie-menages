# 🔒 Accès au Code Source et aux Données

## Pourquoi le code n'est-il pas publié ?

Ce projet académique contient :
- **Code source propriétaire** développé dans le cadre d'un Master 2
- **Données confidentielles** de l'enquête ENSPD 2022

Pour garantir :
- ✅ La protection de la propriété intellectuelle des auteurs
- ✅ La confidentialité des données personnelles des ménages enquêtés
- ✅ Le respect des accords avec l'ENSPD

## 📚 Que trouve-t-on dans ce dépôt ?

### Disponible publiquement :
- ✅ **Rapport complet (PDF)** : Méthodologie, résultats, interprétations
- ✅ **Extraits de code** : Snippets essentiels dans le rapport
- ✅ **Visualisations** : Graphiques et tableaux de résultats
- ✅ **Liste des packages** : `requirements.R` pour reproduire l'environnement
- ✅ **Documentation** : README complet

### Non disponible publiquement :
- ❌ **Scripts R complets** : Code source intégral
- ❌ **Données brutes** : Base ENSPD 2022

## 🔓 Comment accéder au code source complet ?

### Pour qui ?

**Accès accordé pour :**
1. 🎓 **Chercheurs académiques** - Projets de recherche similaires
2. 🔬 **Collaborations scientifiques** - Extensions méthodologiques
3. 📊 **Réplication** - Vérification de reproductibilité
4. 👨‍🏫 **Enseignement** - Usage pédagogique (avec autorisation)

### Procédure de demande

**Étape 1 : Contactez les auteurs**
Envoyez un email aux auteurs (voir section Contact du README) avec :
- Votre nom et affiliation
- Objectif de votre demande
- Description de votre projet/recherche
- Engagement de citation du travail original

**Étape 2 : Accord de confidentialité**
Pour les données ENSPD, un accord avec l'ENSPD peut être nécessaire.

**Étape 3 : Accès au dépôt privé**
Après validation, vous recevrez :
- Accès au dépôt complet
- Support pour la réplication

## 📊 Accès aux Données ENSPD 2022

Les données proviennent de l'**Enquête ENSPD 2022**.

**Pour obtenir les données :**

**Option 1 : Contact direct ENSPD**
- École Nationale de Statistiques, de Planification et de Démographie (ENSPD)
- Bénin
- [djustino87@gmail.omm]

**Option 2 : Via les auteurs**
- Pour collaborations académiques
- Nécessite approbation interne de l'ENSPD

## 🔐 Extrait de Code : Exemples Disponibles

Le rapport PDF contient des extraits de code complets pour :

### Section 3.2 : Estimation des Modèles
```r
# Exemple : Modèle ordonné (extrait)
library(MASS)
modele_ordonne <- polr(Conditions_vie ~ ..., data = donnees, Hess = TRUE)
```

### Section 4.2 : Analyse Descriptive
- Statistiques descriptives
- Tableaux croisés
- Tests du Chi-deux

### Section 4.3 : Validation
- Test de Brant
- Matrice de confusion
- Courbes ROC

**📄 Consultez le rapport complet : `report/Modele_Polytomique.pdf`**

## 📖 Reproductibilité

### Ce que vous pouvez reproduire SANS le code complet :

1. **Installer l'environnement** :
```r
source("requirements.R")
```

2. **Appliquer la méthodologie** :
   - Le rapport décrit chaque étape en détail
   - Les formules mathématiques sont explicites
   - Les packages et fonctions sont identifiés

3. **Comparer les résultats** :
   - Tableaux de coefficients fournis
   - Métriques de performance détaillées
   - Interprétations complètes

### Ce qui nécessite l'accès complet :

- Exécution automatisée de l'analyse
- Modification des spécifications du modèle
- Ajout de nouvelles variables
- Réplication exacte bit-à-bit

## ✉️ Contact

**Pour toute demande d'accès :**

📧 **Email** : [juniorgangnon3553@gmail.com]  
🏫 **Institution** : Université d'Abomey-Calavi - CIPMA-CHAIRE UNESCO  
👤 **Encadrant** : Dr. ATCHADÉ Nicodème

**Délai de réponse** : 3-5 jours ouvrables

---

## 📜 Engagement des Utilisateurs Autorisés

En obtenant l'accès au code source complet, vous vous engagez à :

- ✅ Utiliser le code uniquement à des fins académiques/recherche
- ✅ Citer le travail original dans toute publication
- ✅ Ne pas redistribuer le code sans autorisation
- ✅ Respecter la confidentialité des données ENSPD
- ✅ Informer les auteurs de toute publication utilisant ce travail

---

**Dernière mise à jour** : Novembre 2025  
**Version du projet** : 1.0