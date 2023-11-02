import pygame
import sys

# Initialisation de Pygame
pygame.init()

# Définition de la taille de la fenêtre
largeur, hauteur = 800, 600
ecran = pygame.display.set_mode((largeur, hauteur))

# Couleurs
blanc = (255, 255, 255)
bleu = (0, 0, 255)

# Position du joueur
x, y = 50, 50
largeur_joueur, hauteur_joueur = 40, 60
vitesse = 5

# Boucle de jeu
jeu_en_cours = True
while jeu_en_cours:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            jeu_en_cours = False

    touches = pygame.key.get_pressed()
    if touches[pygame.K_LEFT]:
        x -= vitesse
    if touches[pygame.K_RIGHT]:
        x += vitesse

    # Effacer l'écran
    ecran.fill(blanc)

    # Dessiner le joueur
    pygame.draw.rect(ecran, bleu, (x, y, largeur_joueur, hauteur_joueur))

    pygame.display.update()

# Quitter Pygame
pygame.quit()
sys.exit()
