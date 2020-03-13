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
Chaque classe contient plusieurs documents .


## Distribution des données:
Celon le graphe ci dessous, on remarque des classes dominantes par rapport aux autres, comme les classes Email, Letter, Memo.
![source](/img/distribution_donnees.PNG)

## Pré-Traitement des données:

Cette étape pourrait être primordiale , car c'est une approche qui consiste à supposer que la plus petite unité d'information dans un texte est le mot . Nous allons donc représenter nos textes sous forme de séquences de mots.</br>

Pour cela, on va proceder comme suit:

    * Supprimer les tags html(s'ils existents)
    * Remplacer les ponctuations par des espaces
    * Remplacer les lettres majuscule en minuscule . 
