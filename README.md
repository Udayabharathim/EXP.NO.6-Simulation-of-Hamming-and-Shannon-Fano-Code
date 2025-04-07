# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code


## AIM
 Simulation of Hamming and Shannon-Fano Code

## SOFTWARE REQUIRED
Google Collab

## ALGORITHMS
### Huffman Coding Algorithm
 1.Input the probability of each symbol/message (e.g., P₁, P₂, ..., P₇).
 2.Create leaf nodes for each symbol, sorted by increasing probability.
 3.Repeat until there's only one node left:
 4.Pick the two nodes with the lowest probability.
 5.Combine them into a new node with their summed probability.
 6.Assign 0 and 1 to branches from the new node.
 7.Assign codes to each symbol by tracing the path from the root to the leaf (left → 0, right → 1).

### Shannon–Fano Coding Algorithm
1. Input the probabilities Pi for each symbol.
2. Sort the symbols in descending order of their probability.
3.Divide the list into two parts such that the total probabilities are as equal as possible.
4.Assign 0 to the upper group and 1 to the lower group.
5.Recursively apply the procedure to each group, appending the bit to the existing code.


## PROGRAM

```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```

# OUTPUT
![image](https://github.com/user-attachments/assets/9d934bb0-2431-45a2-819d-c5679e34d987)


 
# RESULT
 Simulation of Hamming and Shannon-Fano Code was verified successfully.
