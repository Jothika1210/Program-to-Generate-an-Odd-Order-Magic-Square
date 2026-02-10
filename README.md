# Program-to-Generate-an-Odd-Order-Magic-Square
import numpy as np

order = int(input("Enter order of magic square (order must be odd): "))

# If even number is given, increment by 1
if order % 2 == 0:
    order = order + 1
    print("Given order is even, so it is incremented by 1.")

magic = np.zeros((order, order), dtype=int)

n = 1
i = 0
j = order // 2  # start from middle of first row

while n <= order*order:
    magic[i][j] = n
    n += 1
    # move diagonally up-right
    new_i = (i - 1) % order
    new_j = (j + 1) % order

    if magic[new_i][new_j]:  # already filled
        i = (i + 1) % order
    else:
        i = new_i
        j = new_j

# Display the magic square
print("\nGenerated Magic Square is:\n")

for row in magic:
    print("|", end="")
    for val in row:
        print(f"{val:4d} |", end="")
    print()
    print("-" * (order * 6))
    output
    Enter order of magic square (order must be odd): 5

Generated Magic Square is:

|  17 |  24 |   1 |   8 |  15 |
------------------------------
|  23 |   5 |   7 |  14 |  16 |
------------------------------
|   4 |   6 |  13 |  20 |  22 |
------------------------------
|  10 |  12 |  19 |  21 |   3 |
------------------------------
|  11 |  18 |  25 |   2 |   9 |
------------------------------

