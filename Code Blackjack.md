""" Aidee par mon grand frere et un forum """
from random import *#pour indiquer qu'on fait intervenir des valeurs au hasard, (d'ou le random=hasard)
from tkinter import*

def score(carte:list) -> int:
    """ Prend une liste de carte e nparamètrre. Les cartes sont décrites par une chaïne de caractères.
        Exemple: 'AS', '0', 'Valet' ...
        Renvoie la valeur en points associée
    """
# ---------------------------------(1) : Valeure des cartes--------------------------------------------
    if carte[0] == '0' :
        return 0
    elif carte[0] == 'AS' :
        AS = input("Une carte AS a ete tiree , quel valeure lui attribuer, 1 ou 11 ?")
        if AS == '1' :
            return 1
        else :
            return 11
    elif carte[0] in ('10' , 'Valet' , 'Dame' , 'Roi'):
        return 10
    else:
        return int(carte[0])

prenom = input("Bienvenue dans le jeu Black jack, Entrez votre prénom : ")
print ("Bonjour,", prenom)
print()

valeur = [ 'AS', '2' , '3' , '4' , '5' , '6' , '7' , '8' , '9' , '10' ,'Valet','Dame','Roi']
couleur = [' de Carreau  ',' de Pique ',' de Trèfle ',' de Coeur']
list = []

#----------------------------------- (2) : Mise du joueurs --------------------------------------------

mise_1 = int(input("Mise d'argent du  joueur (en €) :"))


#-------------------------------- (3) : Reception des cartes--------------------------------------------

print("Chaque joueur recoit 2 Cartes !" )
print("Commencons par le Croupier")
print()   # pour faire des espaces (aerer)


                # A-Croupier

# Reception de la premiere Carte (Croupier)
carte1_Croupier= sample (valeur,1)+ sample (couleur,1)  #"sapmle" est une fonction du random, pour tirer une valeur au hasard, parmi la liste proposee
print("Croupier, Voici votre premiere carte : ")
print(carte1_Croupier)

# Reception de la deuxieme carte (Croupier)
carte2_Croupier = sample (valeur,1) + sample (couleur,1)
print("Voici la seconde : ")
print(carte2_Croupier)

# Total des cartes (Croupier)
total_cartes_Croupier = score(carte1_Croupier) + score(carte2_Croupier)
print("Le score de Croupier  est de ",total_cartes_Croupier)
print()


              # B-joueur

# Reception de la premiere Carte (joueur1)
carte1_j1= sample (valeur,1)+sample (couleur,1)
print(prenom , "voici votre premiere carte : ")
print(carte1_j1)
from random import *#pour indiquer qu'on fait intervenir des valeurs au hasard, (d'ou le random=hasard)
from tkinter import*

def score(carte:list) -> int:
    """ Prend une liste de carte e nparamètrre. Les cartes sont décrites par une chaïne de caractères.
        Exemple: 'AS', '0', 'Valet' ...
        Renvoie la valeur en points associée
    """
# ---------------------------------(1) : Valeure des cartes--------------------------------------------
    if carte[0] == '0' :
        return 0
    elif carte[0] == 'AS' :
        AS = input("Une carte AS a ete tiree , quel valeure lui attribuer, 1 ou 11 ?")
        if AS == '1' :
            return 1
        else :
            return 11
    elif carte[0] in ('10' , 'Valet' , 'Dame' , 'Roi'):
        return 10
    else:
        return int(carte[0])

prenom = input("Bienvenue dans le jeu Black jack, Entrez votre prénom : ")
print ("Bonjour,", prenom)
print()

valeur = [ 'AS', '2' , '3' , '4' , '5' , '6' , '7' , '8' , '9' , '10' ,'Valet','Dame','Roi']
couleur = [' de Carreau  ',' de Pique ',' de Trèfle ',' de Coeur']
list = []

#----------------------------------- (2) : Mise du joueurs --------------------------------------------

mise_1 = int(input("Mise d'argent du  joueur (en €) :"))


#-------------------------------- (3) : Reception des cartes--------------------------------------------

print("Chaque joueur recoit 2 Cartes !" )
print("Commencons par le Croupier")
print()   # pour faire des espaces (aerer)


                # A-Croupier

# Reception de la premiere Carte (Croupier)
carte1_Croupier= sample (valeur,1)+ sample (couleur,1)  #"sapmle" est une fonction du random, pour tirer une valeur au hasard, parmi la liste proposee
print("Croupier, Voici votre premiere carte : ")
print(carte1_Croupier)

# Reception de la deuxieme carte (Croupier)
carte2_Croupier = sample (valeur,1) + sample (couleur,1)
print("Voici la seconde : ")
print(carte2_
# Reception de la deuxieme carte (joueur1)
carte2_j1 = sample (valeur,1) + sample (couleur,1)
print("Voici la seconde carte : ")
print(carte2_j1)

# Total des cartes (joueur1)
total_cartes_j1 = score(carte1_j1) + score(carte2_j1)
print(prenom ,", votre score est de ",total_cartes_j1)
print()
# --------------------------------------(4) : Addition des cartes-----------------------------------------

nvlle_carte = input(" Quel est votre choix :'tirer carte'=1 , 'Main satisaisante' =2 ou 'Doubler la mise  =3 ?")
total_cartes2_Croupier = total_cartes_Croupier
total_cartes2_j1  =total_cartes_j1

              # A-Score Final du Croupier
if total_cartes_Croupier <= 16:
    carte3_Croupier = sample (valeur,1) + sample (couleur,1)
    print("Croupier a un score inferieur ou egal a 16, donc il tire une nouvelle carte :" ,carte3_Croupier)
    total_cartes2_Croupier = score(carte1_Croupier) + score(carte2_Croupier) + score(carte3_Croupier)
    print()
    print("Croupier, Voici le nouveau score :" , total_cartes2_Croupier)
    print()

              # B-Score Finale du Joueur 1
if nvlle_carte == "1" :
    print(prenom , ", voici votre 3e carte :")
    carte3_j1 = sample (valeur,1) + sample (couleur,1)
    print(carte3_j1)
    total_cartes2_j1 = score(carte1_j1) + score(carte2_j1) + score(carte3_j1)
    print()
    print(prenom," Voici votre nouveau score :" , total_cartes2_j1)
    print()

if nvlle_carte == "2":
    total_cartes2_j1 = total_cartes_j1
    print()
    print(prenom,"Voici votre nouveau score : ",total_cartes2_j1)

if nvlle_carte == "3" :
    carte3_j1 = sample (valeur,1) + sample (couleur,1)
    print(carte3_j1)
    mise_1 = mise_1*2
    total_cartes2_j1 = score(carte1_j1) + score(carte2_j1) + score(carte3_j1)
    print()
    print(prenom," Voici votre nouveau score :" , total_cartes2_j1)

# ----------------------------(5) : Qui est le vainqueur ?-------------------------------------------

                # A-A propos du Black Jack
jeu_continue = True
while jeu_continue :

    if total_cartes2_j1 == 21 :
            print()
            print('Blackjack!', prenom , 'a remporter la partie, voici votre argent : ' , mise_1*2 , 'e')
            jeu_continue = False
    if total_cartes2_Croupier == 21 :
            print()
            print('Blackjack!, Le Croupier remporte la partie ! et vous perdez ')
            jeu_continue = False

                # B-L'egalite

    if total_cartes2_j1 ==  total_cartes2_Croupier :  # En cas d'egalite, Pour La somme final du croupier
        print()
        print('Score nul, Personne ne gagne !!!! ')
        jeu_continue = False


               # C-Score le plus elevee, inferieur a 21

    if 21 > total_cartes2_Croupier > total_cartes2_j1 :
        print()
        print("Croupier ",total_cartes2_Croupier, " est superieur a vous",total_cartes2_j1)
        print("Croupier Gagne!!")
        jeu_continue = False

    if 21 > total_cartes2_j1 > total_cartes2_Croupier:
        print()
        print("Vous etes superieur avec",total_cartes2_j1," a ", total_cartes2_Croupier)
        print("Vous gagnez, " , mise_1*2 ,'euros')
        print("fin Bravo")
        jeu_continue = False

    if total_cartes2_Croupier > 21:
        print('Croupier PERD , Vous gagnez!')
        jeu_continue = False

    if total_cartes2_j1 > 21 :
        print('Vous depassez 21 , vous perdez !')
        print("Vous perdez", mise_1, "euros, Croupier remporte la partie")
        jeu_continue = False
