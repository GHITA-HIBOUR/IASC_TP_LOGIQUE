# TP-LOGIQUE
chaînage avant, chaînage arrière et fermeture logique 

# TP1 — Modèles logiques pour l'intelligence artificielle

## 1. Introduction générale

La logique joue un rôle important en intelligence artificielle. Elle permet de représenter des connaissances, d'appliquer des règles et de déduire de nouvelles informations.

Ce TP porte sur la logique propositionnelle, les règles d'inférence, le chaînage avant, le chaînage arrière et la fonction de fermeture. Une application pratique en Python permet d'illustrer ces concepts à travers un système expert basé sur des règles logiques.

## 2. Recherche théorique

### 2.1. Logique propositionnelle

La logique propositionnelle étudie les propositions qui peuvent être vraies ou fausses. Elle utilise différents connecteurs logiques pour construire des expressions.

- **ET (∧)** : les deux propositions sont vraies.
- **OU (∨)** : au moins une proposition est vraie.
- **NON (¬)** : inverse la valeur de vérité d'une proposition.
- **Implication (→)** : représente une relation de type « si P, alors Q ».
- **Équivalence (↔)** : les deux propositions ont la même valeur de vérité.

### 2.2. Prémisses et conclusions

Les prémisses sont les faits ou les conditions de départ d'un raisonnement. La conclusion est l'information déduite à partir de ces prémisses et des règles logiques.

**Exemple :**
- Prémisse 1 : Il pleut.
- Prémisse 2 : S'il pleut, la route est mouillée.
- Conclusion : La route est mouillée.

### 2.3. Règles d'inférence

Les règles d'inférence permettent de déduire une conclusion à partir de prémisses.

**Exemple : le modus ponens**
- Si P, alors Q : P → Q.
- P est vraie.
- Donc Q est vraie.

### 2.4. Chaînage avant

Le chaînage avant (*Forward Chaining*) part des faits connus et applique les règles d'inférence pour déduire de nouveaux faits.

**Exemple :**
- Fait initial : P.
- Règle 1 : P → Q.
- Règle 2 : Q → R.

Résultat : le système déduit Q, puis R.

### 2.5. Chaînage arrière

Le chaînage arrière (*Backward Chaining*) part d'un objectif à démontrer et recherche les règles et les faits nécessaires pour le justifier.

**Exemple :**

Pour démontrer R, le système recherche une règle permettant de déduire R à partir de Q, puis vérifie si Q peut être déduit à partir de P.

Si P est un fait connu, l'objectif R peut être démontré.

### 2.6. Fonction de fermeture

Dans un système de raisonnement à base de règles, la fermeture d'un ensemble de faits consiste à ajouter progressivement les conclusions déductibles à partir des règles disponibles, jusqu'à ce qu'aucun nouveau fait ne puisse être obtenu.

**Exemple :**
- Faits initiaux : {P}.
- Règles : P → Q et Q → R.
- Fermeture obtenue : {P, Q, R}.

## 3. Environnement et outils utilisés

- **Python :** langage utilisé pour implémenter les algorithmes de raisonnement logique.
- **SymPy :** bibliothèque permettant de représenter des propositions logiques, de manipuler des connecteurs comme `And`, `Or`, `Not` et `Implies`, et de vérifier la satisfiabilité avec `satisfiable`.
- **itertools :** module Python utilisé pour générer des combinaisons de valeurs de vérité et construire une table de vérité.

## 4. Application pratique : Système expert basé sur des règles logiques

L'application consiste à développer un système expert simple qui utilise des faits et des règles logiques pour déduire des conclusions concernant les problèmes possibles de démarrage d'un ordinateur.

### Faits

- P : L'ordinateur ne démarre pas.
- Q : Un problème d'alimentation est possible.
- R : Il faut vérifier le chargeur.
- S : La batterie est déchargée.

### Règles d'inférence

- P → Q
- Q → R
- S → Q

Le système applique ces règles à l'aide du chaînage avant, du chaînage arrière et de la fonction de fermeture.

## 5. Tests et résultats

Plusieurs tests permettent d'observer le fonctionnement du système :

- **Test 1 :** l'ordinateur ne démarre pas. Le système déduit Q puis R.
- **Test 2 :** la batterie est déchargée. Le système déduit Q puis R.
- **Test 3 :** aucun fait initial n'est fourni. Aucune nouvelle conclusion n'est déduite.

Ces tests illustrent le rôle des faits initiaux et des règles d'inférence dans la production de nouvelles connaissances.

## 6. Conclusion

Ce TP nous a permis d'étudier plusieurs notions de logique utilisées en intelligence artificielle et de les mettre en pratique avec Python. L'implémentation du chaînage avant, du chaînage arrière et de la fonction de fermeture montre comment un système expert peut exploiter des faits et des règles pour produire des conclusions logiques.
