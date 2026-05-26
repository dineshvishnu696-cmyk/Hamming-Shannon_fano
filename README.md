# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
Google Colab
# Theory:
# Huffman Tree
Huffman tree is a binary tree used for lossless data compression by combining symbols with the lowest probabilities repeatedly. It generates optimal prefix codes with minimum average code length.
# Shannon-Fano Tree
Shannon-Fano tree is a binary tree used for source coding by dividing symbols into groups with nearly equal probabilities. It produces prefix codes but is less efficient than Huffman coding.
# Program:
```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples : "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)

# Avg length of the code word
for k in range(n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

# Entropy
for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)

# Efficiency
eff = hs / L
eff = round(eff, 3)

# Redundancy
red = round(1 - eff, 3)

# Variance
var = 0
for k in range(n):
    var1 = p[k] * ((lk[k] - L) ** 2)
    var = var + var1

var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation:
<img width="892" height="1376" alt="image" src="https://github.com/user-attachments/assets/48d9ace1-2bc7-4cda-8870-567d28277cb3" />

<img width="936" height="1514" alt="image" src="https://github.com/user-attachments/assets/6bc501a1-6008-423c-b637-ca6396c90bf8" />

<img width="907" height="1432" alt="image" src="https://github.com/user-attachments/assets/a3c1dc21-73f4-4e8d-b95c-648257153e1c" />

# Output:
<img width="591" height="445" alt="image" src="https://github.com/user-attachments/assets/5871c655-ffa1-41b3-94e4-a9ad9b8122d0" />
 
# Results:
Thus, the Source Coding Theorem was successfully simulated and verified using Huffman and Shannon-Fano coding techniques. Huffman coding produced better compression efficiency with a lower average code length compared to Shannon-Fano coding.
