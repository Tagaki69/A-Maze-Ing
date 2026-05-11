# MazeGenerator

## Initialize a MazeGenerator

`MazeGenerator` is the reusable class used to generate, solve, display, and export a maze.

This class stores all maze settings and creates the base grid at instantiation.  
Each cell starts with four closed walls: North, East, South, and West.

The `42` pattern is also prepared automatically when the instance is created.  
If the maze is too small to display the pattern, an error message is printed.

If you want to generate another maze cleanly, it is recommended to create a new `MazeGenerator` instance, because the current grid keeps the walls already opened by the previous generation.

---

### How to use it in your own code:
```python
from mazegen import MazeGenerator

# 1. Instantiate the generator
tester = MazeGenerator(width=20, height=12, entry=[0,0], exit_p=[19,11], is_perfect=True)

# 2. Generate the maze (optionally with a specific seed)
tester.generate(seed=42)

# 3. Solve the maze to get the shortest path
path = tester.solve()
print("Path coordinates:", path)

# 4. Export to standard 42 Hex format
tester.export_to_hex("my_output.txt")
```