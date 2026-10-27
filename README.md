# ML_Nikkei_L-N-S
Construire un signal d'achat, de vente ou de neutralité sur le Nikkei 225 pour un investisseur en EUR. En cas d'achat, décider s'il faut couvrir ou non le risque de change JPY/EUR.

Méthode :
Analyse explicative : régression linéaire pour identifier les facteurs qui expliquent la performance de l'indice.
Signal d'achat/neutre/vente : chaque facteur est standardisé (score Z), puis un modèle de classification prédit le mouvement suivant (hausse, stabilité, baisse). Nous partons d'une régression logistique comme référence, puis nous la comparons à des arbres de décision (gradient boosting) et à un réseau de neurones.
+Couverture du yen : un second modèle décide en cas d'achat si une couverture (forward, FX swap ou option) est préférable. Il tient compte de l'écart de taux EUR/JPY et de l'aversion au risque et du sentiment des news.

Données :
Facteurs financiers : Nikkei 225, indices TOPIX par taille et par style (petites vs grandes capitalisations, value vs growth), marchés asiatiques (Taïwan, Chine, Inde, MSCI Emerging Markets), taux souverains 10 ans, volatilité (VIX, Nikkei VI), change USD/JPY et EUR/JPY.
Facteurs extra-financiers : news économiques et politiques, transformées en scores de sentiment et de risque par des modèles de traitement du langage.
Sources : Yahoo Finance, Fred, Kaggle et Bloomberg, de 1999 à aujourd'hui.
