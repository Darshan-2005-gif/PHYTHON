### Conways Game of Life
print("Darshan naik , USN:1AY24AI082, SEC:O")
import numpy as np
import os
import time
ROWS = 20
COLS = 40
SLEEP_TIME = 0.3
def clear_screen():
    os.system('cls' if os.name == 'nt' else 'clear')
def print_grid(grid):
    clear_screen()
    for row in grid:
        line = ''.join(['█' if cell else ' ' for cell in row])
        print(line)
def count_neighbors(grid, x, y):
    total = 0
    for dx in [-1, 0, 1]:
        for dy in [-1, 0, 1]:
            if dx == 0 and dy == 0:
                continue
            nx, ny = (x + dx) % ROWS, (y + dy) % COLS  # wrap around (toroidal)
            total += grid[nx][ny]
    return total
def next_generation(grid):
    new_grid = np.zeros((ROWS, COLS), dtype=int)
    for i in range(ROWS):
        for j in range(COLS):
            neighbors = count_neighbors(grid, i, j)
            if grid[i][j] == 1 and neighbors in (2, 3):
                new_grid[i][j] = 1
            elif grid[i][j] == 0 and neighbors == 3:
                new_grid[i][j] = 1
    return new_grid
def main():
   
    grid = np.random.choice([0, 1], size=(ROWS, COLS), p=[0.8, 0.2])
    try:
        while True:
            print_grid(grid)
            grid = next_generation(grid)
            time.sleep(SLEEP_TIME)
    except KeyboardInterrupt:
        print("\nSimulation stopped by user.")

if __name__ == "__main__":
    main()
