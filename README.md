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

from tkinter import ttk

fenetre = Tk()

label = ttk.Label(fenetre, text=" === VIVE LE CALCUL MENTAL === ")
label.pack()

fenetre.mainloop()
import random # En important le module random cela va nous permettre d'utiliser des fonctions générant des nombres aléatoires.

point = 0


print("\t\t\t\t=== VIVE LE CALCUL MENTAL ===\n\n")
a = int(input("Combien de parties voulez-vous faire ?: " )) # L'utilisateur choisit le nombre de parties qu'il voudra faire.

x = int(input("Vous choisissez le niveau 1 , 2 ou 3 ? : ")) # L'utilisateur introduira un nombre entre 1 et 3 lui permettant de choisir un niveau plus ou moins facile.
vie = 3
 
for i in range (0,a) : # On crée la boucle par rapport au nombre de parties choisies
    
    if x == 1 :
       premier_nombre = random.randint(1,200) # Le premier nombre choisit aléatoirement se situera entre 1 et 200
       second_nombre = random.randint(1,100) # Le second nombre choisit aléatoirement se situera entre 1 et 100
       operation = random.randint(1,2) # Le signe de l'opération sera choisi aléatoirement parmi les signes disponibles en fonction du niveau
       
       if operation == 1 : 
           print(premier_nombre)  
           print('+')  
           print(second_nombre)
           reponseVraie = premier_nombre + second_nombre # Il s'agit du résultat que l'utilisateur est censé obtenir
       else :
           
           print(premier_nombre)  
           print('-')  
           print(second_nombre)
           reponseVraie = premier_nombre - second_nombre 
           
       
    elif x == 2:
       premier_nombre = random.randint(1,50) # Le premier nombre choisit aléatoirement se situera entre 1 et 50
       second_nombre = random.randint(1,20) # Le premier nombre choisit aléatoirement se situera entre 1 et 20
       operation = random.randint(1,3)
       if operation == 1 : 
           print(premier_nombre)  
           print('+')  
           print(second_nombre)
           reponseVraie = premier_nombre + second_nombre
       elif operation == 2 :
           print(premier_nombre)  
           print('-')  
           print(second_nombre)
           reponseVraie = premier_nombre - second_nombre
       else:
           print(premier_nombre)  
           print('*')  
           print(second_nombre)
           reponseVraie = premier_nombre * second_nombre
    elif x == 3 :
       premier_nombre = random.randint(1,100)
       second_nombre = random.randint(1,50)
       operation = random.randint(1,3)
       if operation == 1 : 
           print(premier_nombre)  
           print('+')  
           print(second_nombre)
           reponseVraie = premier_nombre + second_nombre
       elif operation == 2 :
           print(premier_nombre)  
           print('-')  
           print(second_nombre)
           reponseVraie = premier_nombre - second_nombre
       else :
           print(premier_nombre)  
           print('*')  
           print(second_nombre)
           reponseVraie = premier_nombre * second_nombre
           
    else:
        print("Votre choix n'est pas disponible veuillez recommencer !") # L'utilisateur n'a pas choisi un nombre parmi ceux qu'il doit choisir ...
       
    reponseUtilisateur = int(input("Quelle est votre réponse a ce calcul ?")) # L'utilisateur entrera la réponse qu'il pense juste

    while vie > 0 : # Tant que le nombre de vie est supérieure à 0 alors ...
                      
        if reponseUtilisateur != reponseVraie and vie != 1 : # Si l'utilisateur donne une réponse différente de la réponse vraie et que son nombre de vie est différent de 1 alors il a une seconde chance
        
            print("Faux , essaie encore !") 
            vie -= 1 # Le nombre de vie de l'utilisateur diminue de 1
            chance = 1 # L'utilisateur a le droit à un second essai, il peut recommencer.
            
            if chance == 1 :
                reponseUtilisateur2 = int(input("Quelle est votre réponse a ce calcul ?")) # 2ème tentative de l'utilisateur
                
                if reponseUtilisateur2 == reponseVraie : # L'utilisateur a répondu correctement au bout de sa deuxième tentative.
                    print("Enfin c'est pas trop tôt ! ")
                    point += 1 # L'utilisateur gagne 1 point au lieu de 3 ...
                else : 
                    print("Faux , ça fait deux erreurs on change de question !") # L'utilisateur n'a pas trouvé la bonne réponse dommage ...
                    bonne_reponse = 'La bonne réponse était ' + str(reponseVraie) + ' dommage ...' # Puisque l'utilisateur n'a pas trouvé la bonne réponse on lui affiche la bonne réponse.
                    print(bonne_reponse)
                    point += 0 # L'utilisateur ne gagne donc pas de points.
                    
        else:
           print("Du premier coup , bien joué !") # L'utilisateur trouve la bonne réponse du premier coup
           point += 3 # L'utilisateur gagne donc 3 points
           chance = 0 # Il n'a donc pas besoin de chance ...
           
        break # La boucle while s'arrête afin de reprendre un nouveau calcul et que son nombre de vie soit réinitialisé 
    
points_max = a * 3 # Nombre de points maximum que peut obtenir l'utilisateur en fonction de son nombre de partie

reponse = 'Vous avez eu ' + str(point) + ' points sur ' + str(points_max) + ' maximum, bien joué ! ' # A la fin de la partie l'utilisateur voit le nombre de points qu'il a eu au total 

print(reponse) # On lui affiche son nombre de points

