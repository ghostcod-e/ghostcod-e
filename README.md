-pip install pygame
-import pygame
import sys

# Initialize Pygame
pygame.init()

# Constants
WIDTH, HEIGHT = 400, 400
GRID_SIZE = 20
GRID_WIDTH = WIDTH // GRID_SIZE
GRID_HEIGHT = HEIGHT // GRID_SIZE
WHITE = (255, 255, 255)
RED = (255, 0, 0)

# Create the game window
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Simple Game Grid")

# Player attributes
player_x, player_y = 0, 0
player_color = RED

# Main game loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_LEFT:
                player_x -= 1
            elif event.key == pygame.K_RIGHT:
                player_x += 1
            elif event.key == pygame.K_UP:
                player_y -= 1
            elif event.key == pygame.K_DOWN:
                player_y += 1

    # Ensure the player stays within the grid boundaries
    player_x = max(0, min(GRID_WIDTH - 1, player_x))
    player_y = max(0, min(GRID_HEIGHT - 1, player_y))

    # Clear the screen
    screen.fill(WHITE)

    # Draw the player
    pygame.draw.rect(screen, player_color, (player_x * GRID_SIZE, player_y * GRID_SIZE, GRID_SIZE, GRID_SIZE))

    # Update the display
    pygame.display.update()

# Quit Pygame
pygame.quit()
sys.exit()



<!---
ghostcod-e/ghostcod-e is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
