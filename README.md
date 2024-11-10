import pygame
import random

# Initialize Pygame
pygame.init()

# Screen dimensions
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Catch the Falling Apples")

# Colors
WHITE = (255, 255, 255)
RED = (255, 0, 0)
BROWN = (139, 69, 19)

# Game variables
basket_width, basket_height = 100, 20
basket_x = WIDTH // 2 - basket_width // 2
basket_y = HEIGHT - basket_height - 10
basket_speed = 10

apple_radius = 15
apple_x = random.randint(0, WIDTH - apple_radius)
apple_y = -apple_radius
apple_speed = 5

score = 0
font = pygame.font.Font(None, 36)

# Game loop
running = True
while running:
    screen.fill(WHITE)
    
    # Check for events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Move the basket with arrow keys
