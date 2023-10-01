import pygame
import random

pygame.init()

# Definiere die Bildschirmgröße
SCREEN_WIDTH, SCREEN_HEIGHT = 400, 500
SCREEN = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))

# Definiere die Farben
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

# Definiere die Tetromino-Formen
SHAPES = [
    [[1, 1, 1, 1]],  # I-Form
    [[1, 1, 1],
     [0, 1, 0]],     # T-Form
    [[1, 1, 1],
     [1, 0, 0]],     # L-Form
    [[1, 1, 1],
     [0, 0, 1]],     # J-Form
    [[1, 1],
     [1, 1]],        # O-Form
    [[1, 1, 0],
     [0, 1, 1]],     # Z-Form
    [[0, 1, 1],
     [1, 1, 0]]      # S-Form
]

# Initialisiere das Spielfeld
grid = [[0 for _ in range(SCREEN_WIDTH // 25)] for _ in range(SCREEN_HEIGHT // 25)]

# Definiere die Schriftart und den Text
font = pygame.font.Font(None, 36)
score = 0

# Hauptspiel-Schleife
clock = pygame.time.Clock()
fall_time = 0
fall_speed = 0.27
game_over = False

while not game_over:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            game_over = True

    # Bewege den Tetromino nach unten
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT]:
        pass  # Bewege Tetromino nach links
    if keys[pygame.K_RIGHT]:
        pass  # Bewege Tetromino nach rechts
    if keys[pygame.K_DOWN]:
        pass  # Bewege Tetromino schneller nach unten

    # Falle der Tetromino-Stücke
    fall_time += clock.get_rawtime()
    if fall_time / 1000 >= fall_speed:
        fall_time = 0
        pass  # Lass das Tetromino fallen

    # Überprüfe auf vollständige Linien
    pass  # Überprüfe und lösche volle Linien

    # Zeichne das Spielfeld und die Tetrominos
    SCREEN.fill(WHITE)
    pass  # Zeichne das Spielfeld und die Tetrominos

    # Zeige den aktuellen Spielstand an
    text = font.render("Score: " + str(score), True, BLACK)
    SCREEN.blit(text, (50, 20))

    pygame.display.flip()
    clock.tick(60)  

pygame.quit()
