EXERCICS DE NETTOYAGE DE DONNÉES AVEC PYTHON


PROJET 1 : Analysons des factures d'énergie
1. Introduction
Un des cas d'usage fréquents de l'analyse de données est ce qu'on appelle la détection d'anomalies. Il s'agit en fait de checker, à travers des gros jeux de donnnées, s'il n'y a pas des éléments de la chaîne de production qui dysfonctionnent.

Le contrôle de la facturation est un cas d'école intéressant. Comme la consommation d'énergie n'est pas facilement interprétable par un humain, il peut être utile de vérifier les factures émises par les fournisseurs d'énergie afin de repérer d'éventuelles erreurs et, le cas échéant, permettre à l'entreprise d'économiser de l'argent.

2. Le projet
2.1. La mission
L'opérateur de télécommunications national en Slovaquie fait appel à vous pour contrôler ses factures d'électricité. Il vous explique que les réseaux mobiles (et plus directement, les antennes) sont très consommateurs d'énergie. C'est pourquoi, en tant qu'opérateur, il doit dépenser chaque année de très fortes sommes dans l'électricité.

En revanche, il a le sentiment (et certains de ses salariés lui ont confirmé cela) qu'il y a des erreurs dans les factures et que certaines sommes ne sont pas justifiées. Mais il y a un nombre de factures colossal et son service de comptabilité n'a pas les compétences nécessaires pour traiter autant de données.

Il vous demande donc de récupérer ici le fichier qui regroupe toutes les factures pour l'ensemble des antennes de l'opérateur. Et de le nettoyer pour que les équipes terrain puissent l'utiliser régulièrement, dès qu'un besoin de vérification sera remonté.

Finalement, ton objectif est de transformer le fichier qu'a récupéré la direction en un fichier exploitable. Pour les équipes de comptabilité, "exploitable" signifie qu'ils n'ont qu'à rechercher le nom d'une antenne en particulier, et ils peuvent obtenir l'historique de sa consommation d'énergie pour vérifier s'il y a des anomalies. Pour que cet historique soit intéressant, ils ont besoin d'avoir la consommation moyenne journalière (comme ça par ex, ils peuvent comparer un mois de Février qui fait 28 jours avec un mois de janvier qui fait 31 jours, sans se dire que la diminution vient de la différence de jours dans un mois).

2.2. Les tâches
1) Le nom d'une antenne a un format bien précis : il est toujours composé de 4 chiffres et de deux lettres. On te demande de retirer tout autre caractère de la colonne "SITE_NAME".
2) On te demande de supprimer la colonne "INVOICE_NAME" qui n'apporte rien aux équipes.
3) Il y a des antennes pour lesquelles on a des factures mensuelles tandis que pour d'autres, on les reçoit moins régulièrement (trimestre, semestre, année). Ajoute une colonne à ton tableau qui calcule le nombre de jours entre le début de la période de facturation et la fin de la période de facturation.
4) A partir de cette nouvelle colonne, crée une autre colonne qui nous donne la consommation journalière moyenne de la période.
5) Merci d'ajouter également une colonne qui donne, pour chaque antenne, le nombre de factures dont on dispose au total. Pas grave si l'information se répète à chaque ligne pour une même antenne.
6) Et information bonus si tu y arrives : les équipes aimeraient beaucoup avoir une liste de toutes les antennes avec, pour chaque antenne, le coefficient de variation de la consommation. Cela permettra d'avoir une idée, pour chaque antenne, de la dispersion de sa consommation d'énergie.
7) Enfin, tu dois exporter ces deux fichiers obtenus pour pouvoir l'envoyer aux équipes de l'opérateur et leur demander si c'est bien cela qu'ils attendaient de toi.

3. Rendu attendu
Un fichier .ipynb qui contient l'ensemble de tes analyses.
Le fichier csv final, beaucoup plus clean et exploitable par les équipes de comptabilité. Et si tu as réussi cette étape, l'autre fichier csv qui donne la liste des coefficients de variation.


Projet 2 : Analysons la qualité de l'air

Analysons la qualité de l'air
1. Introduction
Après ta mission chez l'opérateur de télécoms, tu as voulu changer d'univers et rejoindre le monde des ONGs. Tu as trouvé un poste chez OpenAQ, une organisation à but non lucratif qui permet aux communautés du monde entier de purifier leur air en harmonisant, en partageant et en utilisant des données ouvertes sur la qualité de l'air.

Ils te préviennent tout de suite que l'enjeu principal n'est pas forcément de collecter les données mais surtout de réussir à les harmoniser. C'est en mettant l'ensemble des données collectées au même format qu'on peut ensuite réaliser des comparaisons intéressantes 🌎

2. Le projet
OpenAQ souhaiterait mettre en ligne sur son site un fichier qui permet de comparer des mesures de l'air récentes, relevées sur un jour donné, partout dans le monde. Pour cela, on te demande de nettoyer les données dont on dispose pour l'instant.

Tu as reçu un mail de ton manager qui te dit : "Télécharge le jeu de données disponible sur la plateforme Opendatasoft (ici si le lien n'est plus à jour). Et renvoie-moi d'ici la fin de la journée un fichier csv qui ne comporte aucune erreur, ni information non exploitable. Merci et bon courage."

Comme le message est un peu lapidaire, on va te donner quelques informations supplémentaires. Regarde sur l'onglet Informations du jeu de données, deux disclaimers sont énoncés :

Some records contain encoding issues on specific characters; those issues are present in the raw API data and were not corrected.
Some dates are set in the future: those issues also come from the original data and were not corrected 🥴
Cela te donne une idée de ce qu'il va falloir nettoyer en premier lieu !

Si tu souhaites plus de précision dans les consignes, voici les étapes qu'on te conseille de suivre pour arriver à tes fins :

Supprimer les données qui ne concernent pas la journée du 06-08-2021.
Supprimer les données qui sont illisibles et pour lesquelles on ne comprend pas la ville concernée.
Pour chaque polluant, vérifier qu'on n'a qu'une seule mesure utilisée. Autrement, supprimer les données qui correspondent à la mesure minoritaire ou moins cohérente.
Regarder s'il y a des valeurs aberrantes ou des problèmes par rapport à notre objectif final (pouvoir comparer des mesures sur un maximum de pays) et noter ces aspects dans un fichier texte.
3. Rendu attendu
Le fichier csv qui ne comporte aucune erreur ni information non exploitable.
Un fichier txt qui précise les limites du fichier final