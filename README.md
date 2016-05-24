# Projet---Un-peu-de-calcul-mental

## Quelques idées

- Niveau facile : 2 chiffres pour + et - , 1 chiffre pour * 
- Niveau moyen : 3 chiffres pour + et - , 1 nombre a 1 chiffre et 1 nombre a 2 chiffres pour * 
- NIveau difficile : 4  chiffres pour - et + , 2 chiffres pour * 
- systeme facile de points ; bonne réponse 3 pts , bonne réponse a la deuxieme tenta 1 pts sinon 0. 10 sec / question 
- systeme moyen de points ; bonne réponse 5 pts , bonne réponse a la deuxieme tenta 3 pts sinon 1. 1 min/question
- systeme difficile de points ; bonne réponse 7 pts , bonne réponse a la deuxieme tenta 5 pts sinon 3. 2min/question

- Pas de bonne réponse avant fin de temps : 0 pts
- Systeme de questions , 15 questions 5 facile , 5 moyen et 5 difficile. 
- A la fin afficher les calculs posés avec les réponses que l'utilisateur a mit et la bonne réponse ainsi que le nombre de point gagné par question/ points totaux.

import time # En important le module time , on va pouvoir utiliser le temps dans notre programme 
import random # En important le module random cela va nous permettre d'utiliser des fonctions générant des nombres aléatoires.

continuer = True # On initialise la variable pour qu'elle puisse rentrer dans la boucle while

while continuer: # La boucle while permet à l'utilisateur de lancer le programme autant de fois qu'il le souhaitera
    
    nombre_parties = int(input("Combien de parties voulez-vous faire? : ")) # On génère une variable qui permettera à l'utilisateur de choisir le nombre de parties qu'il voudra faire
    
    print('Le niveau 4 correspond aux tables de multiplication apprises en primaire')
    
    niveau = int(input("Vous choisissez le niveau 1 , 2 , 3 ou 4 ? : ")) # L'utilisateur introduira un nombre entre 1 et 3 lui permettant de choisir un niveau plus ou moins facile.
    
    point = 0 # On initialise le nombre de points de l'utilisateur
    
    vie = 3 # Permet à l'utilisateur d'avoir 3 vies au début de la partie
    
    temps_manche = 0 # On initialise le temps total
    
    for i in range (0,nombre_parties) : # On crée la boucle par rapport au nombre de parties choisies
        
        debut = time.time() # On enregistre le temps lorsque le programme se lance 
        
        if niveau == 1 : # Permet de choisir la difficulté au rang facile
            
           premier_nombre = random.randint(1,200) # Le premier nombre choisit aléatoirement se situera entre 1 et 200
           second_nombre = random.randint(1,100) # Le second nombre choisit aléatoirement se situera entre 1 et 100
           operation = random.randint(1,2) # Le signe de l'opération sera choisi aléatoirement parmi les signes disponibles en fonction du niveau
           
           if operation == 1 : # Choisis le signe addition parmi ceux disponibles au niveau facile
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' + ' + str(second_nombre) + ' ?' # Calculer la somme du premier et du second nombre
               print(calcul)
               reponseVraie = premier_nombre + second_nombre # Réponse que l'utilisateur doit entrer pour avoir la bonne réponse
               
           else :  # Choisis l'autre signe disponible puisqu'il n'y en a que deux disponibles au niveau facile
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' - ' + str(second_nombre) + ' ?'  # Calculer la différence du premier et du second nombre
               print(calcul)
               reponseVraie = premier_nombre - second_nombre
               print(calcul) 
               reponseVraie = premier_nombre - second_nombre
           
        elif niveau == 2: # Permet de choisir la difficulté au rang moyen 
            
           premier_nombre = random.randint(1,50) # Le premier nombre choisit aléatoirement se situera entre 1 et 50
           second_nombre = random.randint(1,20) # Le premier nombre choisit aléatoirement se situera entre 1 et 20
           operation = random.randint(1,3)
           
           if operation == 1 :  # Choisis le signe addition parmi ceux disponibles au niveau moyen
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' + ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre + second_nombre 
               
           elif operation == 2 : # Choisis le signe de soustraction parmi ceux disponibles au niveau moyen
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' - ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre - second_nombre
               
           else: # Choisis le dernier signe disponible , multiplication parmi ceux disponibles au niveau moyen
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' x ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre * second_nombre
               
        elif niveau == 3 : # Permet de choisir la difficulté au rang difficile
            
           premier_nombre = random.randint(1,100)
           second_nombre = random.randint(1,50)
           operation = random.randint(1,3)
           
           if operation == 1 : 
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' + ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre + second_nombre
               
           elif operation == 2 :
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' - ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre - second_nombre
               
           else :
               
               calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' x ' + str(second_nombre) + ' ?' 
               print(calcul) 
               reponseVraie = premier_nombre * second_nombre
               
        elif niveau == 4 :
            
            premier_nombre = random.randint(1,10)
            second_nombre = random.randint(1,10)
            calcul = 'Quel est le résultat de ' + str(premier_nombre) + ' x ' + str(second_nombre) + ' ?' # On détermine quel est le résultat du produit de premier et du second nombre
            print(calcul) 
            reponseVraie = premier_nombre * second_nombre
            
               
        else:
            print("Votre choix n'est pas disponible veuillez recommencer !") # L'utilisateur n'a pas choisi un nombre parmi ceux qu'il doit choisir ...
           
        reponseUtilisateur = int(input("Quelle est votre réponse a ce calcul ? ")) # L'utilisateur entrera la réponse qu'il pense juste
    
        while vie > 0 : # Tant que le nombre de vie est supérieure à 0 alors ...
                          
            if reponseUtilisateur != reponseVraie : # Si l'utilisateur donne une réponse différente de la réponse vraie et que son nombre de vie est différent de 1 alors il a une seconde chance
            
                print("Faux , essaie encore !") 
                vie -= 1 # Le nombre de vie de l'utilisateur diminue de 1
                chance = 1 # L'utilisateur a le droit à un second essai, il peut recommencer.
                
                if chance == 1 : # Si l'utilisateur n'a pas réussi dès le premier coup, il a une chance supplémentaire pour trouver le résultat
                    
                    reponseUtilisateur2 = int(input("Quelle est votre réponse a ce calcul ?")) # 2ème tentative de l'utilisateur
                    
                    if reponseUtilisateur2 == reponseVraie : # L'utilisateur a répondu correctement au bout de sa deuxième tentative.
                    
                        print("Enfin c'est pas trop tôt ! ")
                        point += 1 # L'utilisateur gagne 1 point au lieu de 3 ...
                        fin = time.time() # On enregistre le temps écoulé une seconde fois
                        temps_total = int(fin) - int(debut) # On soustrait les deux durées enregistrées pour voir combien de temps il s'est écoulé entre les deux prises de temps
                        phrase_temps = 'Tu as pris ' + str(temps_total) + ' secondes pour répondre à un simple calcul ? Dépêche toi !'
                        print(phrase_temps)
                        print(" ") # Permet de sauter une ligne entre chaque calcul
                        temps_manche += temps_total # On ajoute au temps total le temps que l'utilisateur a mis à cette manche
                        
                    else : 
                        
                        print("Faux , ça fait deux erreurs on change de question !") # L'utilisateur n'a pas trouvé la bonne réponse dommage ...
                        bonne_reponse = 'La bonne réponse était ' + str(reponseVraie) + ' dommage ...' # Puisque l'utilisateur n'a pas trouvé la bonne réponse on lui affiche la bonne réponse.
                        print(bonne_reponse)
                        point += 0 # L'utilisateur ne gagne donc pas de points.
                        fin = time.time()
                        temps_total = int(fin) - int(debut) # On soustrait le temps à la fin de la partie au temps au début de la partie
                        phrase_temps = 'Tu as pris ' + str(temps_total) + ' secondes pour répondre à un simple calcul sans trouver la réponse ? Ba bravo !'
                        print(phrase_temps)
                        print(" ")
                        temps_manche += temps_total # On a joute au temps total le temps que l'utilisateur a mis pour répondre au calcul 
            else:
                
               print("Du premier coup , bien joué !") # L'utilisateur trouve la bonne réponse du premier coup
               point += 3 # L'utilisateur gagne donc 3 points
               chance = 0 # Il n'a donc pas besoin de chance ...
               fin = time.time()
               temps_total = int(fin) - int(debut)
               phrase_temps = 'Tu as pris ' + str(temps_total) + ' secondes pour répondre à un simple calcul ? Dépêche toi !' # Le temps qu'a mis l'utilisateur à répondre au calcul
               print(phrase_temps)
               print(" ")
               temps_manche += temps_total
            break # La boucle while s'arrête afin de reprendre un nouveau calcul et que son nombre de vie soit réinitialisé 
        
    points_max = nombre_parties * 3 # Nombre de points maximum que peut obtenir l'utilisateur en fonction de son nombre de partie
    
    reponse = 'Vous avez eu ' + str(point) + ' points sur ' + str(points_max) + ' maximum, bien joué ! ' # On prépare la phrase que le programme affichera en y mettant les points obtenus par l'utilisateur
    
    reponse_temps = 'Vous avez pris ' + str(temps_manche) + ' secondes pour répondre à ' + str(nombre_parties) + ' calculs... ' # On détermine le nombre de secondes que l'utilisateur a mis au jeu 
    
    if vie == 0 : #Si l'utilisateur n'a plus de vie (...)
        
        print('Il ne vous reste plus de vies , fin du jeu ! ')
        print(reponse) # On lui affiche son nombre de points
        print(reponse_temps)
        Nouvelle_partie = input("Nouvelle partie ? ") # (...) on lui propose de recommencer une nouvelle partie
        
    else : 
        
        print(reponse) # On lui affiche son nombre de points
        print(reponse_temps)
        Nouvelle_partie = input("Nouvelle manche ? ") # On lui propose de recommencer une nouvelle partie
    
    if Nouvelle_partie not in ('o', 'oui', 'ok' , 'yes'): # Si l'utilisateur répond par les réponses proposées dans la parenthèse alors il recommence une partie ...
    
        continuer = False # ... sinon il quitte le jeu

