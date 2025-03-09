# Guide des Cartes Mémoire Anki

## Introduction

Ce document explique comment créer, formater et utiliser efficacement les cartes mémoire Anki pour optimiser votre apprentissage. Anki est un système de répétition espacée qui vous aide à mémoriser des informations de manière efficace en vous présentant les cartes juste avant que vous ne les oubliez.

## Pourquoi utiliser Anki pour apprendre ?

Anki est un outil puissant pour l'apprentissage de nouvelles connaissances pour plusieurs raisons :

- **Répétition espacée scientifique** : Anki utilise un algorithme qui détermine le moment optimal pour revoir chaque carte, maximisant la rétention à long terme tout en minimisant le temps d'étude.
- **Apprentissage actif** : Force votre cerveau à récupérer activement l'information, renforçant les connexions neuronales.
- **Personnalisation** : Adaptable à n'importe quel sujet d'étude, des langues aux sciences en passant par la médecine ou la programmation.
- **Efficacité prouvée** : Des recherches en sciences cognitives montrent que la répétition espacée est jusqu'à 74% plus efficace que les méthodes d'étude traditionnelles.
- **Portabilité** : Disponible sur tous les appareils, permettant d'étudier n'importe où et n'importe quand.
- **Mesure des progrès** : Fournit des statistiques détaillées sur votre apprentissage et votre rétention.

## Table des matières

1. [Formats de cartes](#formats-de-cartes)
2. [Création de fichiers d'importation](#création-de-fichiers-dimportation)
3. [Importation dans Anki](#importation-dans-anki)
4. [Types de cartes spécifiques](#types-de-cartes-spécifiques)
5. [Conseils d'optimisation d'apprentissage](#conseils-doptimisation-dapprentissage)
6. [Ressources additionnelles](#ressources-additionnelles)

## Formats de cartes

### Cartes basiques (Question/Réponse)

Les cartes basiques contiennent une question et une réponse. C'est le format le plus simple et le plus courant.

**Exemple:**
```
Quelle est la capitale de la France ?    Paris
```

### Cartes à trous (Cloze)

Les cartes à trous comportent du texte avec des parties masquées que vous devez retrouver. Elles sont parfaites pour apprendre des concepts dans leur contexte.

**Exemple:**
```
La capitale de la France est {{c1::Paris}}.
```

Quand vous étudiez, Anki affiche : "La capitale de la France est _____."

## Création de fichiers d'importation

### Structure de base d'un fichier d'importation

```
#separator:tab
#html:true/false
#notetype:Basic/Cloze
#deck:Nom du paquet

Question/Texte    Réponse
```

### En-têtes importants

- `#separator:tab` - Indique que les champs sont séparés par des tabulations
- `#html:true/false` - Autorise ou non le HTML dans les cartes
- `#notetype:Basic` - Pour les cartes question/réponse standard
- `#notetype:Cloze` - Pour les cartes à trous
- `#deck:Nom du paquet` - Spécifie dans quel paquet importer les cartes

### Séparateurs valides

- `tab` - Tabulation (recommandé)
- `comma` - Virgule
- `semicolon` - Point-virgule
- `pipe` - Barre verticale |

## Importation dans Anki

1. Enregistrez votre fichier au format texte (.txt)
2. Dans Anki, allez dans Fichier → Importer
3. Sélectionnez votre fichier texte
4. Vérifiez que les paramètres d'importation correspondent à votre fichier:
  - Type de note correct (Basic ou Cloze)
  - Séparateur correct (tab)
  - Option "Permettre le HTML dans les champs" cochée si vous utilisez du HTML
5. Cliquez sur Importer

### Gestion des erreurs courantes

- **Problème**: Cartes à trous importées comme cartes basiques
  - **Solution**: Vérifiez que `#notetype:Cloze` est correctement spécifié au début du fichier

- **Problème**: Champs mal séparés
  - **Solution**: Assurez-vous d'utiliser le bon séparateur (habituellement tab) de manière cohérente

- **Problème**: Images non importées
  - **Solution**: Les images doivent être dans un sous-répertoire "collection.media" d'Anki ou importées séparément

## Types de cartes spécifiques

### Cartes avec média

Pour inclure des images dans vos cartes:

```
#html:true

"<img src=""nom_image.jpg"">"    Réponse à la question sur cette image
```

Les fichiers d'images doivent être placés dans le dossier de média d'Anki.

### Cartes à trous multiples

Vous pouvez créer plusieurs trous dans une même carte:

```
Paris est la capitale de la {{c1::France}} et se trouve sur la {{c2::Seine}}.
```

Cette carte génère deux questions différentes:
1. "Paris est la capitale de la _____ et se trouve sur la Seine."
2. "Paris est la capitale de la France et se trouve sur la _____."

### Cartes à choix multiples

```
#html:true

Quel est le plus grand pays du monde?
A) Chine
B) États-Unis
C) Russie
D) Canada    La réponse est C) Russie avec une superficie de 17 098 246 km².
```

## Conseils d'optimisation d'apprentissage

### Structure optimale des cartes

1. **Principe de la carte minimale**: Une carte = Une information
2. **Questions précises**: Évitez les questions vagues ou ambiguës
3. **Contexte suffisant**: Incluez juste assez de contexte pour comprendre
4. **Mémorisation active**: Formulez les questions pour stimuler la réflexion

### Quand utiliser les cartes basiques vs à trous

- **Cartes basiques** (Question/Réponse):
  - Pour des concepts entiers
  - Pour des définitions
  - Pour des relations cause-effet
  - Quand la réponse est unique et précise

- **Cartes à trous** (Cloze):
  - Pour mémoriser des éléments dans leur contexte
  - Pour des listes ou séquences
  - Pour des formules
  - Pour mémoriser des termes spécifiques dans une phrase

### Structuration cognitive efficace

1. **Encodage élaboré**: Reliez l'information à ce que vous connaissez déjà
2. **Images mentales**: Créez des représentations visuelles
3. **Associations significatives**: Reliez l'information à quelque chose de personnel
4. **Récupération espacée**: Utilisez Anki régulièrement selon son algorithme

## Ressources additionnelles

### Sites web utiles

- [Documentation officielle d'Anki](https://docs.ankiweb.net/)
- [AnkiWeb](https://ankiweb.net/) - Pour synchroniser vos cartes entre appareils
- [Reddit r/Anki](https://www.reddit.com/r/Anki/) - Communauté d'utilisateurs

### Extensions recommandées

- **Image Occlusion Enhanced**: Pour créer des cartes à trous sur des images
- **Review Heatmap**: Visualiser votre activité d'étude
- **Hierarchical Tags**: Mieux organiser vos étiquettes
- **AwesomeTTS**: Ajouter de l'audio à vos cartes

### Livres sur l'apprentissage efficace

- "Make It Stick: The Science of Successful Learning" par Peter C. Brown
- "Fluent Forever" par Gabriel Wyner
- "Moonwalking with Einstein" par Joshua Foer

## Exemples de fichiers d'importation

### Exemple de fichier pour cartes basiques

```
#separator:tab
#html:false
#notetype:Basic
#deck:Géographie

Quelle est la capitale de la France ?    Paris
Quelle est la capitale de l'Italie ?    Rome
Quelle est la capitale de l'Espagne ?    Madrid
```

### Exemple de fichier pour cartes à trous

```
#separator:tab
#html:false
#notetype:Cloze
#deck:Capitales

La capitale de la {{c1::France}} est {{c2::Paris}}.    
La capitale de l'{{c1::Italie}} est {{c2::Rome}}.    
La capitale de l'{{c1::Espagne}} est {{c2::Madrid}}.    
```

---

Ce guide a été créé pour vous aider à maximiser votre apprentissage avec Anki. N'hésitez pas à l'adapter selon vos besoins spécifiques.