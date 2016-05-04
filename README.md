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

import random
point = 0


print("\t\t\t\t=== VIVE LE CALCUL MENTAL ===\n\n")
a = int(input("Combien de parties voulez-vous faire ?: " )) 

x = int(input("Vous choisissez le niveau 1 , 2 ou 3 ? : "))

 
for i in range (0,a) :
    vie = 3
    if x == 1 :
       premier_nombre = random.randint(1,100)
       second_nombre = random.randint(1,200)
       operation = random.randint(1,2)
       if operation == 1 : 
       		print(int(premier_nombre) + '+' + int(second_nombre))
       		reponseVraie = premier_nombre + second_nombre
       else :
       		print(int(premier_nombre) + '-' + int(second_nombre))
       		reponseVraie = premier_nombre - second_nombre
       
       
    elif x == 2:
       premier_nombre = random.randint(1,50)
       second_nombre = random.randint(1,20)
       operation = random.randint(1,3)
       if operation == 1 : 
       		print(int(premier_nombre) + '+' + int(second_nombre))
       		reponseVraie = premier_nombre + second_nombre
       elif operation == 2 :
       		print(int(premier_nombre) + '-' + int(second_nombre))
       		reponseVraie = premier_nombre - second_nombre
       else:
       		print(int(premier_nombre) + '*' + int(second_nombre))
       		reponseVraie = premier_nombre * second_nombre
    else:
       premier_nombre = random.randint(1,100)
       second_nombre = random.randint(1,50)
       operation = random.randint(1,3)
       if operation == 1 : 
       		print(int(premier_nombre) + '+' + int(second_nombre))
       		reponseVraie = premier_nombre + second_nombre
       elif operation == 2 :
       		print(int(premier_nombre) + '-' + int(second_nombre))
       		reponseVraie = premier_nombre - second_nombre
       else :
       		print(int(premier_nombre) + '*' + int(second_nombre))
       		reponseVraie = premier_nombre * second_nombre
       
    reponseUtilisateur = int(input("Quelle est votre réponse a ce calcul ?")

    if vie > 0 :
        
        if reponseUtilisateur != reponseVraie and vie == 1 :
        	print("Faux , ça fait deux erreurs donc on change de question ! ")
    		point += 0
			vie -= 1
        elif reponseUtilisateur == reponseVraie and vie != 3 :
        	print("Enfin c'est pas trop tôt ! ")
        	point += 1 
    	   elif 
    		print("Faux , essaie encore !") 
        	vie -= 1 
    	   else:
        	print("Du premier coup , bien joué !")
        	point += 3
