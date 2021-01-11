# «Une fonction pour les gouverner toutes»

Les ingénieurs pros savent que les programmes doivent être entretenus au fil du temps.
Donc, au moins il y a de code, au moins il faut en faire l'entretien et c'est du temps de gagné.
Une méthode pour réduire la quantité de code de notre programme est de «factoriser» les fonctions qui présentent des similitudes.
Par exemple, si `f(n) = n * 2` et `g(n) = n * 2 + 3`, il est préférable de redéfinir `g` comme suit : `g(n) = f(n) + 3`.
Ainsi, nous profitons du fait que la multiplication de `n` n'est implémentée qu'à un seul endroit.
Le code écrit une seule fois est, du fait, utilisé plusieurs fois.

Les fonctions de chiffrement que vous avez implémentées pour l'exercice 2 offrent cette possibilité.
Reconnaissez que le chiffrement de César n'est en fait qu'un cas particulier du chiffrement de Vigenère.
De même, le chiffrement ROT13 n'est qu'un cas particulier du chiffrement César.
De plus, comme ces fonctions de chiffrement sont symmétriques (l'algorithme est essentiellement le même que l'on chiffre ou que l'on déchiffre), il est possible d'opérer une opération de déchiffrage en faisant appel à la fonction de chiffrage et en ajustant la clé donnée de sorte que le chiffrage produise un effet de déchiffrage !

## Objectif

Revenez sur votre exercice 2 contenant les fonctions de chiffrement.
Créez une nouvelle branche nommée `bonus`.
Gardez cette branche séparée; je ne vous demande pas de la fusionner à la branche `master`.
Sur cette branche, mofifiez votre code pour que toutes les fonctions sauf la fonction `chiffre_Vigenere` soit implémentées en terme des autres fonctions suivant ce tableau :

| Fonction | Fait appel à |
|:- |:- |
| `chiffre_ROT13` | `chiffre_Cesar` |
| `dechiffre_ROT13` | `chiffre_ROT13` |
| `chiffre_Cesar` | `chiffre_Vigenere` |
| `dechiffre_Cesar` | `chiffre_Cesar` |
| `dechiffre_Vigenere` | `chiffre_Vigenere` |
| `chiffre_Vigenere_flux_texte` | `chiffre_Vigenere` |
| `dechiffre_Vigenere_flux_texte` | `chiffre_Vigenere_flux_texte` |

Bien entendu, pour certaines des fonctions de déchiffrage, il vous faudra «inverser» la clé donnée avant de faire appel à la fonction demandée.
Assurez-vous évidemment que tous les tests passent toujours à 100%.

