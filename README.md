
# Mini Projet 1 : Construction d'un Système d'Analyse de Sentiment pour les Critiques de Films

# Introduction:

Ce mini-projet vous demande de mettre en œuvre un système d'analyse de sentiment similaire à celui du chapitre 8 de votre livre. Vous appliquerez les compétences et techniques abordées dans les chapitres 1 à 6 pour accomplir cette tâche. De plus, vous intégrerez la bibliothèque CodeCarbon pour mesurer l'empreinte carbone de votre modèle, discuterez des implications éthiques de votre système d'IA et explorerez le déploiement de votre modèle sur des systèmes embarqués avec des ressources de calcul et de mémoire limitées.

Le modèle d'apprentissage automatique à utiliser dans ce projet est la régression logistique. La régression logistique est un algorithme bien adapté aux tâches de classification de sentiment et fournit des prédictions interprétables. Vous entraînerez, évaluerez et déploierez ce modèle tout au long du projet.
Vous devrez également créer un dépôt GitHub avec un fichier README détaillé qui inclut la documentation du projet, les informations de licence et les meilleures pratiques pour la publication et la maintenance responsables du code. Le livrable final comprend un dépôt GitHub avec une documentation et une licence appropriées.


# Tâches et Objectifs :
    1. Préparation des Données
        ◦ Objectif : Charger et inspecter l'ensemble de données IMDb contenant des critiques de films étiquetées avec des sentiments positifs et négatifs. (https://ai.stanford.edu/%7Eamaas/data/sentiment/) 
        ◦ Tâche : Lire l'ensemble de données, stocker les critiques et leurs sentiments associés, et explorer l'ensemble de données pour comprendre sa structure. 

    2. Prétraitement du Texte
        ◦ Objectif : Nettoyer et prétraiter les données textuelles pour supprimer le bruit et les préparer à l'analyse. 
        ◦ Tâche : Supprimer les caractères inutiles (par exemple, les balises HTML, la ponctuation), convertir le texte en minuscules et traiter les mots en supprimant les mots vides (stop words) et en effectuant une racinisation/lemmatisation. 

    3. Extraction de Caractéristiques
        ◦ Objectif : Transformer le texte nettoyé en caractéristiques numériques pour l'apprentissage automatique. 
        ◦ Tâche : Utiliser une technique de vectorisation telle que TF-IDF pour convertir le texte en une matrice numérique qui capture l'importance de chaque mot dans l'ensemble de données. 

    4. Entraînement du Modèle
        ◦ Objectif : Entraîner un modèle d'apprentissage automatique pour classer les critiques en fonction de leur sentiment. 
        ◦ Tâche : Diviser l'ensemble de données en ensembles d'entraînement et de test, entraîner un modèle de régression logistique et évaluer ses performances sur les données de test. 

    5. Évaluation du Modèle
        ◦ Objectif : Évaluer les performances de votre modèle en utilisant des métriques appropriées. 
        ◦ Tâche : Évaluer la précision, le rappel et le score F1 du modèle de régression logistique. Utiliser ces métriques pour identifier les forces et les faiblesses de votre système. Visualiser la matrice de confusion pour mieux comprendre comment le modèle classe les critiques positives et négatives. 
        ◦ De plus, tester le modèle avec une nouvelle critique, la prétraiter, faire une prédiction et afficher le résultat. Exemple : testez-le avec une nouvelle critique telle que : "Le film avait de superbes visuels, mais l'histoire était terne et prévisible." Le résultat attendu pourrait être : Sentiment négatif. 

    6. Réglage des Hyperparamètres
        ◦ Objectif : Optimiser votre modèle de régression logistique en ajustant ses hyperparamètres. 
        ◦ Tâche : Utiliser une méthode d'optimisation pour trouver les meilleurs paramètres pour votre modèle et améliorer sa précision. 

    7. Analyse de la Courbe d'Apprentissage
        ◦ Objectif : Diagnostiquer les performances de votre modèle en traçant des courbes d'apprentissage. 
        ◦ Tâche : Analyser les performances d'entraînement et de validation en fonction de la taille de l'ensemble d'entraînement pour identifier les problèmes de sous-apprentissage ou de sur-apprentissage. 

    8. Analyse de l'Empreinte Carbone avec CodeCarbon
        ◦ Objectif : Quantifier et discuter de l'empreinte carbone de votre modèle en utilisant la méthodologie CodeCarbon. 
        ◦ Tâche : Installer et intégrer CodeCarbon dans votre projet. Suivre et rapporter les émissions de carbone de votre modèle. Vous pouvez trouver les informations nécessaires ici : https://mlco2.github.io/codecarbon/ & https://codecarbon.io/ 

    9. Considérations Éthiques et Explicabilité
        ◦ Objectif: Discuter de l'éthique dans l'utilisation et le déploiement de votre solution basée sur l'IA en recherchant et en mettant en œuvre des méthodes d'explicabilité appropriées. 
        ◦ Tâche: Comprendre comment un modèle d'apprentissage automatique fait des prédictions est crucial pour assurer la transparence, l'équité et la responsabilité dans le déploiement de l'IA. L'une des techniques largement utilisées pour l'explicabilité du modèle est SHAP (SHapley Additive exPlanations), qui aide à déterminer dans quelle mesure chaque caractéristique (mot) contribue à une prédiction. Dans cette tâche, vous utiliserez SHAP pour analyser l'impact des mots individuels sur la classification des sentiments. Cela vous permettra de visualiser quels mots augmentent ou diminuent la probabilité d'une prédiction de sentiment positif ou négatif. De plus, discuter des aspects clés tels que les biais potentiels dans le modèle, l'équité des résultats et la responsabilité dans la prise de décision de l'IA. Vous pouvez trouver plus d'informations ici : https://shap.readthedocs.io/en/latest/generated/shap.Explanation.html 
        
    10. Considérations de Déploiement pour les Systèmes Embarqués
        ◦ Objectif : Optimiser et convertir le modèle de régression logistique entraîné pour le déploiement sur des systèmes embarqués comme Arduino. 
        ◦ Tâche : Pour déployer le modèle de régression logistique entraîné sur un système embarqué aux ressources limitées comme un Arduino, nous devons optimiser et convertir le modèle dans un format adapté à l'exécution dans un environnement avec une mémoire et une puissance de traitement limitées. Étant donné que les systèmes embarqués ne prennent pas en charge l'exécution directe des modèles d'apprentissage automatique entraînés en Python, nous extrayons les paramètres appris du modèle, à savoir les poids et le biais, après l'entraînement. Ces paramètres sont ensuite quantifiés en entiers à virgule fixe pour éliminer le besoin de calculs en virgule flottante, qui sont inefficaces sur les microcontrôleurs. Une fois la quantification appliquée, nous générons un fichier d'en-tête C++ .h contenant les coefficients et le biais du modèle, formatés de manière à permettre une utilisation directe dans un sketch Arduino. Le modèle final est optimisé pour effectuer une inférence en utilisant l'arithmétique entière, ce qui le rend à la fois léger et efficace pour le déploiement sur les microcontrôleurs. Vous pouvez trouver plus d'informations ici : https://medium.com/@thommaskevin/tinyml-binomial-logistic-regression-0fdbf00e6765 

# Exigences relatives au Dépôt GitHub et à la Documentation :
Vous devez créer un dépôt GitHub pour votre projet et inclure les éléments suivants :
    • Un fichier README détaillé qui comprend : 
        ◦ Aperçu et objectifs du projet 
        ◦ Instructions pour le téléchargement et le prétraitement de l'ensemble de données 
        ◦ Étapes d'entraînement et d'évaluation du modèle 
        ◦ Résultats de l'analyse de l'empreinte carbone 
        ◦ Considérations éthiques et méthodes d'explicabilité 
        ◦ Aperçus du déploiement sur les systèmes embarqués 
    • Une section sur les responsabilités de la publication du code: 
    • Définissez votre responsabilité concernant la publication du code source. 
    • Justifiez l'inclusion d'une licence open-source appropriée (par exemple, MIT, Apache, GPL) et discutez de ses implications. 
    • Comparez différentes pratiques de publication de code et la manière dont elles affectent la transparence, la collaboration et la maintenance logicielle. 
    • Décrivez un protocole de signalement et de correction des bogues (par exemple, suivi des problèmes, demandes d'extraction/pull requests).
