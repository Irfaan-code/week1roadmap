# week1roadmap
semaine 1 de la raodmap pour devenir un ingénieur IA &amp; Big Datadef division(a,b):
  import logging
  logging.basicConfig(level = logging.INFO) 
  logger = logging.getLogger("division")
  logger.debug("tu peux ??")
  logger.info("le programme demarre")
  try:
    x = a/b
    return x 
  except ZeroDivisionError:
    logger.error("on ne peut pas diviser par zero") 
    return "on ne peut pas diviser par zero"
def test_division():
    assert division(10,2) ==5
    assert division(3,0) == "on ne peut pas diviser par zero"
    print("tests okk")

print(division(15,0.0003))
print(division(5,2))
print(division(7,0))

test_division()

try:
    x = int("abc")   # conversion impossible
except ValueError as e:
    print("Erreur:", e)

def commande (prix , *args,**kwargs):
  """  
  calculer le prix final d une commande 
  parametre :
  -prix (float) : prix de base (obligatoire)
  -args(float) : reduction en pourcentage
  -kwargs : cout additionnel :
  livraison(float): montant fixe (par defaut 5)
  emballage(float): montant fixe (par default 2)
  remise_fixe(float): montant fixe (par defaut 0)

  retour :
  -float : prix final apres reduction et coup additionnel 
  """
  prix_reduit = prix - prix * (sum(args))/100
  default = { "livraison":5, "emballage":2 ,"remise_fixe":0}
  default.update(kwargs)
  prix_final = prix_reduit + prix * (default["livraison"] + default["emballage"] - default["remise_fixe"]) /100
  print( "le prix final est :") 
  return f" {prix_final}{' EUR'} "
print(commande(1000 , 3,4,4,livraison=10,emballage = 20 , remise_fixe = 15 )) 
print(commande(25000, 13,livraison = 2, emballage = 8))

def facture (prix , *args,**kwargs):
  """
    Calcule une facture finale.

    Paramètres:
    - prix (float): prix de base obligatoire.
    - *args (float): réductions en pourcentage (ex: 10 pour -10%, 5 pour -5%).
    - **kwargs: options de coût additionnel. Clés supportées:
        - livraison (float): montant fixe ajouté (par défaut 0).
        - autres clés sont ignorées sauf si tu veux les intégrer.

    Retour:
    - float: prix final après réductions et options.
    """
  prix_reduit = prix - prix * (sum(args))/100
  default = { "livraison " : 0}
  default.update(kwargs)
  prix_final = prix_reduit + prix * default["livraison"]/100
  return prix_final
print(facture(
    100,7,3,5, livraison=8
)) 


[{'type': 'singleSelect',
  'question': 'Que représente *args dans une fonction Python ?',
  'options': ["Une liste d'arguments nommés",
   "Un tuple d'arguments positionnels",
   'Un dictionnaire vide',
   'Un paramètre obligatoire'],
  'answer': [1],
  'explanation': '*args capture tous les arguments positionnels sous forme de tuple.'},
 {'type': 'singleSelect',
  'question': 'Que représente **kwargs dans une fonction Python ?',
  'options': ["Un tuple d'arguments",
   "Un dictionnaire d'arguments nommés",
   'Une liste de valeurs',
   'Un paramètre unique'],
  'answer': [1],
  'explanation': '**kwargs capture les arguments nommés sous forme de dictionnaire.'},
 {'type': 'singleSelect',
  'question': 'Que fait defaults.update(kwargs) ?',
  'options': ['Supprime les clés de kwargs',
   'Fusionne kwargs dans defaults',
   'Crée une copie vide',
   'Inverse les clés et valeurs'],
  'answer': [1],
  'explanation': '.update() ajoute ou remplace les clés de kwargs dans defaults.'},
 {'type': 'singleSelect',
  'question': 'Quel est le résultat de moyenne(10,20,30) avec la fonction donnée ?',
  'options': ['10', '20.0', '30', 'Erreur'],
  'answer': [1],
  'explanation': 'La moyenne est (10+20+30)/3 = 20.0.'},
 {'type': 'singleSelect',
  'question': 'Que se passe-t-il si moyenne() est appelée sans argument ?',
  'options': ['Retourne 0',
   'Retourne None',
   'Lève ValueError',
   'Retourne une liste vide'],
  'answer': [2],
  'explanation': "La fonction lève ValueError car aucun argument n'est fourni."},
 {'type': 'singleSelect',
  'question': 'À quoi sert une docstring ?',
  'options': ['Documenter une fonction',
   'Exécuter du code',
   'Créer un dictionnaire',
   'Remplacer les paramètres'],
  'answer': [0],
  'explanation': 'Une docstring est une chaîne de documentation intégrée.'},
 {'type': 'singleSelect',
  'question': "Comment accéder à la docstring d'une fonction ?",
  'options': ['help(ma_fonction)',
   'print(ma_fonction)',
   'ma_fonction()',
   'doc(ma_fonction)'],
  'answer': [0],
  'explanation': 'La fonction help() affiche la docstring.'},
 {'type': 'singleSelect',
  'question': 'Que retourne configuration(batch=64) ?',
  'options': ["{'lr':0.01,'batch':32}",
   "{'lr':0.01,'batch':64}",
   "{'batch':64}",
   'Erreur'],
  'answer': [1],
  'explanation': 'La valeur par défaut batch=32 est remplacée par 64.'},
 {'type': 'singleSelect',
  'question': 'Quelle est la différence entre *args et **kwargs ?',
  'options': ['Aucune différence',
   '*args = tuple, **kwargs = dict',
   '*args = dict, **kwargs = tuple',
   'Les deux sont des listes'],
  'answer': [1],
  'explanation': '*args capture un tuple, **kwargs capture un dictionnaire.'},
 {'type': 'singleSelect',
  'question': 'Que fait return f"{price:.{decimals}f} {currency}" dans format_price ?',
  'options': ['Retourne un nombre',
   'Retourne une chaîne formatée avec prix et devise',
   'Retourne un dictionnaire',
   'Retourne None'],
  'answer': [1],
  'explanation': 'Cela formate le prix en chaîne avec le nombre de décimales et la devise.'}]
