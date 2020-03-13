# Classification des documents du procès des groupes américains du tabac

## But du Projet:
<p>
	Le but de ce travail est d'analyser et de classifier un échantillon de données , qui sont des document colléctés et numérisé, et qui peuvent être désignés comme preuve de l'existance d'un lien entre la consommation du Tabac et des maladies graves.
</p>


## Les données:
<p>Les données qu'on a à notre possession ont été classés dans des répertoires correspondants aux classes de documents:</p>

*Advertisement
*Email
*Form
*Letter
*Memo
*News
*Note
*Report
*Resume
*Scientific </br>
Chaque classe contient plusieurs documents.


#### Distribution des données:
Celon le graphe ci dessous, on remarque des classes dominantes par rapport aux autres, comme les classes Email, Letter, Memo.
![source](/img/distribution_donnees.PNG)

#### Pré-Traitement des données:

On commancepar une approche qui consiste à supposer que la plus petite unité d'information dans un texte est le mot . Nous allons donc représenter nos textes sous forme de séquences de mots.</br>

Pour cela, on va proceder comme suit:

    * Supprimer les tags html(s'ils existents)
    * Remplacer les ponctuations par des espaces
    * Remplacer les lettres majuscule en minuscule . 


#### Séparation des données :

En géneral on a besoin de 2 sets de données, Training et Testing.

	> Training set :ou le jeu de données d'apprentissage , est le jeu de données initial utilisé pour former un algorithme afin de comprendre comment appliquer des technologies telles que les réseaux de neurones, pour apprendre et produire des résultats complexes. Il inclut les données d'entrée et la sortie attendue correspondante. Le but du jeu de données d'apprentissage est de fournir à votre algorithme des données de «vérité sur le terrain».
	> Testing set : ou le jeu de données de test, cependant, est utilisé pour évaluer le degré de l'apprentissage de votre algorithme . Vous ne pouvez pas simplement réutiliser le jeu de données d'apprentissage lors de la phase de test car l'algorithme "connaît" déjà la sortie attendue, ce qui va à l'encontre de l'objectif de test de l'algorithme.

On peut ajouter un 3ème set qui est le jeu de donnée de validation ,qui sert en géneral à fournir une évaluation non biaisée d'un ajustement de modèle sur l'ensemble de données d'apprentissage tout en ajustant les hyperparamètres du modèle (par exemple, le nombre d'unités cachées dans un réseau de neurones ). Les jeux de données de validation peuvent être utilisés pour la régularisation en arrêtant tôt: arrêtez la formation lorsque le nombre d'erreurs sur le jeu de données de validation augmente, car il s'agit d'un signe de surajustement pour le jeu de données de formation.

![source](/img/Separation_donnees.PNG)

## Classification :

Trois types de classifieurs utilisés:
	> Classifieur Bayesien Naif .
	> Reseau de neurones Convolutionnel (CNN).
	> Reseau de neuronnes Multi couches (MLP).

L'objectif est de preserver le classifieur avec le plus grand score , pour cela je vais utiliser 3 metriques d'evaluation (Precision, Recall ,F1 score).

Ainsi je vais utiliser les matrices de confusion pour chaque classifieur , qui est , dans la terminologie de l'apprentissage supervisé, un outil servant à mesurer la qualité d'un système de classification

Dans python , sklearn.metrics propose 2 librairies:classification_report, confusion_matrix.


#### 1.Classifieur Bayesien Naif

<strong>Vectorisation </strong>:Pour appliquer des algorithmes d'apprentissage automatique au texte, les documents doivent être transformés en vecteurs.
J'ai utilisé ce classifieur pour 3 representations differents:

> Bag of Word
> Word Level TF-IDF
> N-gram Level TF-IDF

<strong>Representation Bag of Word </strong>: Le moyen le plus simple et le plus classique de transformer un document en vecteur est l’encodage en sac de mots.

- Définir l'ensemble de tous les mots possibles pouvant figurer dans un document; notez sa taille par max_features.
- Pour chaque document, encodez-le avec un vecteur de taille max_features, avec la valeur de la ième composante du vecteur égale au nombre de fois où le ième mot apparaît dans le document.
<strong>Word level TF-IDF</strong> : MAtrice representant les scores tf-idf de chaque terme dans les differents documents.

<strong>N-gram Level TF-IDF </strong>:N-grams est la combinaison de N termes . Et cette Matrice represente les scores tf-idf de N_grams.

On remarque que les resultats du classifieur bayésien avec une representation (N_gram Level TF_IDF) donne de mailleur resultats que les autres representation.