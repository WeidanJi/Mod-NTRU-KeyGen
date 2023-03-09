# Mod-NTRU-KeyGen

# Generate the module NTRU instance

R = Z[x]/(x^n + 1)

F in R^{k * k} invertible mod q

g in R^k

h = F^(-1) * g mod q

A = [1 h] in R^{k + 1}

B = (g -F \\ g_0 -f_0) in R^{(k + 1) * (k + 1)}

# We should achieve

(1) B * A = 0 mod q

(2) The Gram-Schmidt norm of matrix B is small.

# Difficulty
Generate the trapdoor matrix B, we need to 

(1) calculate the inverse of F mod q

(2) compute f * G - g * F = q (f = det(-F), G = g_0, g = adj(-F) * g[0], F = f_0[0])

(3) reduce F and G by F = F - k * f, G = G - k * g. The definition of k is 
![image](https://user-images.githubusercontent.com/43646022/223951458-84c374de-5326-4767-aa11-cf08788a1bc3.png)

we need to compute the inverse of a ring element.

# Refer
Code: https://github.com/tprest/ModFalcon

This code is by python while not sagemath, the time complexity is high.

Paper: 

(1) [DLP14]Efficient Identity-Based Encryption over NTRU Lattices

(2) [CPS+19] ModFalcon: Compact Signatures Based On Module-NTRU Lattices
