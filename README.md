# Déterminants des Conditions Socio-économiques de Vie des Ménages

## 📊 Projet d'Analyse Statistique - Modèles Polytomiques

Analyse des déterminants socio-économiques des conditions de vie des ménages au Bénin à partir des données ENSPD 2022.

> ** Note importante** : Le code source complet et les données ne sont pas publics.  
>  Consultez [CODE_ACCESS.md](CODE_ACCESS.md) pour les conditions d'accès.

### 🎓 Contexte Académique

**Institution:** Université d'Abomey-Calavi  
**Programme:** Master 2 - Statistique Appliquée aux Vivants  
**Chaire:** CIPMA-CHAIRE UNESCO  
**Année Académique:** 2025-2026  
**Encadrant:** Dr. ATCHADÉ Nicodème

### 👥 Équipe de Projet

- GANGNON Junior
- SESSOU G. Pascal
- YESSIFOU Chabi André
- CODJO Eliab

---

## 📖 Description du Projet

Ce projet applique des **modèles de régression polytomique** (ordonné et non ordonné) pour identifier les facteurs déterminants du niveau socio-économique des ménages, catégorisé en trois modalités : **Faible**, **Moyen** et **Élevé**.

### Objectifs Principaux

1. Identifier les déterminants socio-économiques des conditions de vie
2. Comparer les modèles polytomiques ordonnés vs non ordonnés
3. Valider les hypothèses statistiques (test de Brant, proportionnalité des odds)

---

## 📂 Structure du Projet

```
.
├── README.md                     
├── outputs/
│   ├── figures/                      # Graphiques générés
│   ├── tables/                       # Tableaux de résultats
├── report/
│   └── Modele_Polytomique.pdf        # Rapport complet (60 pages)
├── requirements.R                     # Packages R nécessaires
└── .gitignore                        # Fichiers à exclure de Git
```

---

## 🔧 Installation et Prérequis

### Logiciels Requis

- **R** >= 4.0.0
- **RStudio** (recommandé)

### Packages R Nécessaires

```r
# Installer tous les packages nécessaires
install.packages(c(
  "MASS",           # Modèle ordonné (polr)
  "nnet",           # Modèle multinomial
  "brant",          # Test de proportionnalité
  "car",            # Tests diagnostiques (VIF)
  "lmtest",         # Tests statistiques
  "pROC",           # Courbes ROC et AUC
  "DescTools",      # Pseudo R²
  "effects",        # Effets marginaux
  "dplyr",          # Manipulation de données
  "tidyverse",      # Suite tidyverse
  "knitr",          # Tableaux
  "kableExtra",     # Tableaux avancés
  "ggplot2",        # Visualisations
  "gridExtra",      # Grilles de graphiques
  "readxl",         # Lecture Excel
  "caret",          # Machine learning
  "stargazer",      # Tableaux de régression
  "magrittr"        # Pipe operators
))
```

Ou utiliser le fichier `requirements.R` :

```r
source("requirements.R")
```

---

## 🚀 Utilisation

### 1. Cloner le Dépôt

```bash
git clone https://github.com/JuniorGANGNON/determinants-conditions-vie-menages.git
cd determinants-conditions-vie-menages
```

### 2. Consulter le Rapport

Le rapport complet avec méthodologie, résultats et extraits de code est disponible dans :
```
report/Modele_Polytomique.pdf
```

### 3. Reproduire l'Analyse

**Packages nécessaires :**
```r
source("requirements.R")
```

**Code principal :** Les extraits de code essentiels sont documentés dans le rapport PDF (Section 3 : Mise en œuvre des modèles, Section 4 : Résultats).

### 4. Contact pour le Code Source Complet

Le code source complet est disponible sur demande pour :
- Collaborations académiques
- Projets de recherche similaires
- Vérification de reproductibilité

📧 Contactez les auteurs (voir section Contact ci-dessous).

---

## 📊 Données

### Source
**Enquête ENSPD 2022** - École Nationale de Statistiques, de Planification et de Démographie

### Échantillon
- **N = 1954 ménages**
- Localisation : Parakou, Bénin

### Accès aux Données

Les données brutes ne sont **pas incluses** dans ce dépôt pour des raisons de confidentialité.

**Pour accéder aux données :**
- Contactez l'**ENSPD** (École Nationale de Statistiques, de Planification et de Démographie, Bénin)
- Ou contactez les auteurs du projet pour des collaborations académiques

### Variables

#### Variable Dépendante
- **Conditions_de_vie** : Faible (8.85%) | Moyen (64.02%) | Élevé (27.12%)
  - Construite par Classification Hiérarchique Ascendante (CAH) + AFCM
  - Basée sur biens matériels (électricité, équipements, logement, eau, etc.)

#### Variables Explicatives

**Démographiques:**
- Sexe du chef de ménage
- Âge du chef (15-95 ans)
- Taille du ménage (1-23 personnes)

**Socioculturelles:**
- Ethnie (9 modalités)
- Religion (4 modalités)
- Statut matrimonial (6 modalités)

**Capital Humain:**
- Niveau d'instruction (Aucun, Primaire, Secondaire, Supérieur)

---

## 🔬 Méthodologie

### Modèles Estimés

#### 1. Modèle Polytomique Ordonné (Ordered Logit)

**Hypothèse clé:** Proportionnalité des odds (testée par test de Brant)

*Détails dans le rapport, Section 2.1*

#### 2. Modèle Polytomique Non Ordonné (Multinomial Logit)

**Avantage:** Pas de contrainte de proportionnalité

*Détails dans le rapport, Section 2.2*

### Sélection de Variables
- **Méthode:** Sélection stepwise bidirectionnelle (stepAIC)
- **Critère:** AIC (Akaike Information Criterion)

*Code complet dans le rapport, Section 3.2*

### Tests et Validation

| Test | Objectif | Résultat |
|------|----------|----------|
| **Test de Brant** | Hypothèse de proportionnalité | Rejeté (p<0.001) → Modèle multinomial retenu |
| **Test du rapport de vraisemblance** | Significativité globale | p<0.001 (modèle significatif) |
| **Test de Wald** | Significativité individuelle | 13/22 coefficients significatifs |
| **VIF** | Multicolinéarité | VIF max<5 (aucun problème) |
| **AUC (One-vs-Rest)** | Capacité discriminante | 0.705 (Bon) |
| **Matrice de confusion** | Précision de classification | 66.38% |

*Analyses détaillées dans le rapport, Section 4.4*

---

## 📈 Résultats Principaux

### Facteurs Déterminants (Niveau "Élevé" vs "Faible")

#### 🎓 **Éducation** (Facteur le plus puissant)
- **Niveau supérieur:** OR = 37.18 (p<0.001) → Multiplie par 37 les chances
- **Niveau secondaire:** OR = 6.72 (p<0.001) → Multiplie par 7 les chances
- **Effet marginal:** +30 points de % pour le supérieur

#### 👴 **Âge du Chef de Ménage**
- **60+ ans:** OR = 30.09 (p<0.001) → 30 fois plus de chances
- **45-59 ans:** OR = 22.22 (p<0.001)
- **30-44 ans:** OR = 4.68 (p<0.001)
- **Effet marginal:** +46 points de % à 60 ans vs 15-29 ans

#### 👨‍👩‍👧‍👦 **Taille du Ménage** (Effet négatif pour grandes familles)
- **9+ personnes:** OR = 0.14 (p<0.01) → 7 fois moins de chances d'être "Moyen"
- **6-8 personnes:** OR = 0.48 (p<0.05) → 2 fois moins de chances

### Interprétation Générale

> **"L'éducation supérieure est le levier le plus puissant pour améliorer les conditions de vie. Un chef de ménage diplômé du supérieur a 37 fois plus de chances d'avoir un niveau de vie élevé qu'une personne sans éducation."**

---

## 📉 Limites du Modèle

### Forces
✅ Taux de classification global acceptable (66.38%)  
✅ Capacité discriminante bonne (AUC = 0.71)  
✅ Aucune multicolinéarité  
✅ Modèle globalement significatif

### Faiblesses
❌ **Incapacité à identifier les ménages "Faible"** (F1-score = 0%)  
❌ Confusion importante entre "Élevé" et "Moyen" (73% mal classés)  
❌ Déséquilibre des classes (Faible = 8.85% seulement)  
❌ Pseudo R² modéré (McFadden = 0.10)

### Recommandations d'Amélioration
1. **Rééquilibrage des classes** (SMOTE, sur-échantillonnage)
2. **Ajout de variables spécifiques à la pauvreté** (sécurité alimentaire, accès services de base)
3. **Recalibrage des seuils de décision**
4. **Modèles avec pénalisation des erreurs sur "Faible"**

---

## 📚 Références Clés

1. **Attanasso MO** (2004). *Analyse des déterminants de la pauvreté monétaire des femmes chefs de ménage au Bénin*. Mondes en développement, 128(4):41-63.

2. **Maïga et al.** (2023). *Analyse des déterminants des conditions de vie des ménages ruraux du Mali*. IJSMES, 2(3).

3. **PNUD Bénin** (2017). *Rapport sur la croissance inclusive au Bénin*.

---

## 📄 Documentation

- **Rapport complet:** [Modele_Polytomique.pdf](report/Modele_Polytomique.pdf) (60 pages)
- **Annexes techniques:** Incluses dans le rapport

---

## 🤝 Contribution

### Accès au Code Source Complet

Le code source complet est disponible **sur demande** pour :

✅ **Collaborations académiques** - Projets de recherche conjoints  
✅ **Réplication scientifique** - Vérification de reproductibilité  
✅ **Extensions méthodologiques** - Amélioration des modèles  

**Pour obtenir l'accès :**
1. Contactez les auteurs par email (voir section Contact)
2. Décrivez brièvement votre projet ou intention
3. Acceptez de citer le travail original

### Proposer des Améliorations

Si vous avez des suggestions sans besoin du code complet :
1. Ouvrez une **Issue** sur ce dépôt
2. Décrivez votre suggestion méthodologique ou conceptuelle
3. Les auteurs pourront l'intégrer dans une future version

---

## 📧 Contact

Pour toute question, collaboration ou accès au code source complet :

**Équipe du Projet :**
- GANGNON Junior - [juniorgangnon3553@gmail.com]
- SESSOU G. Pascal 
- YESSIFOU Chabi André - [yessifouchabiandre@gmail.com]
- CODJO Eliab 


**Institution :**
- Université d'Abomey-Calavi
- CIPMA-CHAIRE UNESCO
- Bénin

**Objet du contact :**
- 🤝 Collaborations académiques
- 📊 Accès aux données ou code source
- 📚 Utilisation pédagogique
- 🔬 Projets de recherche similaires

---

## 📜 Licence

Ce projet est développé dans un cadre académique à l'Université d'Abomey-Calavi.

---

## 🙏 Remerciements

- Dr. ATCHADÉ Nicodème pour son encadrement
- ENSPD pour la mise à disposition des données
- Université d'Abomey-Calavi - CIPMA-CHAIRE UNESCO
- Tous les contributeurs du projet

---

## 📊 Statistiques du Projet

![GitHub last commit](https://img.shields.io/github/last-commit/JuniorGANGNON/determinants-conditions-vie-menages)
![GitHub repo size](https://img.shields.io/github/repo-size/JuniorGANGNON/determinants-conditions-vie-menages)
![GitHub language count](https://img.shields.io/github/languages/count/JuniorGANGNON/determinants-conditions-vie-menages)

---

**⭐ Si ce projet vous est utile, n'hésitez pas à lui donner une étoile !**
