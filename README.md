# Projet-morpion
morpion Clément et Simon

#ici on créer la fenetre
from tkinter import *
from tkinter.messagebox import *
def Clic(event):
    global a,C1,C2,C3,C1RC,C1R,C2RC,C2R,C3RC,C3R,L1RC,L1R,L2RC,L2R,L3RC,L3R,L1,L2,L3
    # position du pointeur de la souris
    X = event.x
    Y = event.y
 
    #Si a=1 on met une croix
    if a==1:
        if X < 100:
            if Y < 100:
                if C1[0]==2:
                    a=0
                    C1[0]=1
                    L1[0]=1
                    Croix(50,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
            else :
                if Y < 200:
                    if C1[1]==2:
                        a=0
                        C1[1]=1
                        L2[0]=1
                        Croix(50,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
                else :
                    if C1[2]==2:
                        a=0
                        C1[2]=1
                        L3[0]=1
                        Croix(50,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
        if X < 200 and X > 100:
            if Y < 100:
                if C2[0]==3:
                    a=0
                    C2[0]=1
                    L1[1]=1
                    Croix(150,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
            else :
                if Y < 200:
                    if C2[1]==3:
                        a=0
                        C2[1]=1
                        L2[1]=1
                        Croix(150,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
                else :
                    if C2[2]==3:
                        a=0
                        C2[2]=1
                        L3[1]=1
                        Croix(150,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
        if X < 300 and X > 200:
            if Y < 100:
                if C3[0]==4:
                    a=0
                    C3[0]=1
                    L1[2]=1
                    Croix(250,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
            else :
                if Y < 200:
                    if C3[1]==4:
                        a=0
                        C3[1]=1
                        L2[2]=1
                        Croix(250,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
                else :
                    if C3[2]==4:
                        a=0
                        C3[2]=1
                        L3[2]=1
                        Croix(250,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
    #Ici a=0 et on met un rond
    else:
        if X < 100:
            if Y < 100:
                if C1[0]==2:
                    a=1
                    C1[0]=0
                    L1[0]=0
                    Rond(50,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
            else :
                if Y < 200:
                    if C1[1]==2:
                        a=1
                        C1[1]=0
                        L2[0]=0
                        Rond(50,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
                else :
                    if C1[2]==2:
                        a=1
                        C1[2]=0
                        L3[0]=0
                        Rond(50,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
        if X < 200 and X > 100:
            if Y < 100:
                if C2[0]==3:
                    a=1
                    C2[0]=0
                    L1[1]=0
                    Rond(150,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
            else :
                if Y < 200:
                    if C2[1]==3:
                        a=1
                        C2[1]=0
                        L2[1]=0
                        Rond(150,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
                else :
                    if C2[2]==3:
                        a=1
                        C2[2]=0
                        L3[1]=0
                        Rond(150,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
        if X < 300 and X > 200:
            if Y < 100:
                if C3[0]==4:
                    a=1
                    C3[0]=0
                    L1[2]=0
                    Rond(250,50)
                else :
                        showinfo(title='Non',message='Tu ne peux pas !')
            else :
                if Y < 200:
                    if C3[1]==4:
                        a=1
                        C3[1]=0
                        L2[2]=0
                        Rond(250,150)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
                else :
                    if C3[2]==4:
                        a=1
                        C3[2]=0
                        L3[2]=0
                        Rond(250,250)
                    else :
                        showinfo(title='Non',message='Tu ne peux pas !')
 
#ici on créer la fonction pour afficher les ronds
def Rond(x1,y1):
    global C1,C2,C3
    Canevas.create_oval(x1-45,y1-45,x1+45,y1+45,width=4)
    Verif()
#ici on créer la fonction pour afficher les croix
def Croix(x1,y1):
    global C1,C2,C3
    Canevas.create_line(x1-45,y1-45,x1+45,y1+45,width=4)
    Canevas.create_line(x1+45,y1-45,x1-45,y1+45,width=4)
    Verif()
#ici on créer la fonction qui compte les points
def Verif():
    global C1, C2,C3,C1RC,C1R,C2RC,C2R,C3RC,C3R,L1RC,L1R,L2RC,L2R,L3RC,L3R,L1,L2,L3
    C1RC = C1.count(1)
    C1R = C1.count(0)
    C2RC = C2.count(1)
    C2R = C2.count(0)
    C3RC = C3.count(1)
    C3R = C3.count(0)
 
    L1RC = L1.count(1)
    L1R = L1.count(0)
    L2RC = L2.count(1)
    L2R = L2.count(0)
    L3RC = L3.count(1)
    L3R = L3.count(0)
 
 
    #ici on affiche le joueur qui a gagner 
    if C1RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if C1R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
    if C2RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if C2R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
    if C3RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné!')
    if C3R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
 
    if C1[0]==1 and C2[1]==1 and C3[2]==1: 
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if C1[2]==1 and C2[1]==1 and C3[0]==1: 
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')    
 
    if C1[0]==0 and C2[1]==0 and C3[2]==0: 
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
    if C1[2]==0 and C2[1]==0 and C3[0]==0: 
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')  
 
    if L1RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if L1R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
    if L2RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if L2R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
    if L3RC == 3:
        showinfo(title='Gagne',message='Joueur 1 a Gagné !')
    if L3R == 3:
        showinfo(title='Gagne',message='Joueur 2 a Gagné !')
 
 
#ici on initialise les colones et les lignes
 
C1RC,C1R,C2RC,C2R,C3RC,C3R,L1RC,L1R,L2RC,L2R,L3RC,L3R = 0,0,0,0,0,0,0,0,0,0,0,0
 
 
 
a=1
 
C1=[2,2,2]
L1=[2,2,2]
 
C2=[3,3,3]
L2=[3,3,3]
 
C3=[4,4,4]
L3=[4,4,4]
 
print(C1)
 
 
 
 
# Création de la fenêtre principale
Mafenetre = Tk()
Mafenetre.title("Morpion")
# Création d'un widget Canvas
Largeur = 300
Hauteur = 300
Canevas = Canvas(Mafenetre, width = Largeur, height =Hauteur, bg ="white")
# La méthode bind() permet de lier un événement avec une fonction :
# un clic gauche sur la zone graphique provoquera l'appel de la fonction utilisateur Clic()
Canevas.bind("<Button-1>", Clic)
Canevas.pack(padx =5, pady =5)

#ici on créer les lignes qui délimite les colones et les cases
Canevas.create_line(0,100,300,100,fill="darkred",width=4)
 
Canevas.create_line(0,200,300,200,fill="darkred",width=4)
 
Canevas.create_line(100,300,300,-100000,fill="darkred",width=4)
 
Canevas.create_line(200,300,300,-100000,fill="darkred",width=4)
 
 
# Création d'un widget Button (bouton Quitter)
Button(Mafenetre, text ="Quitter", command = Mafenetre.destroy).pack(side=LEFT,padx=5,pady=5)
 
Mafenetre.mainloop()
