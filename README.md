# Prime_factorisation_grover_algorithm

# Grovers_Algo

## QCG Open Project 1: Using Grover’s Algorithm for Factorization of Bi-Primes

### Problem Statement

#### Overview

Factoring large integers into their prime components is a fundamental problem with significant implications in cryptography and information security. Traditional algorithms, like Shor's algorithm, have demonstrated superpolynomial speedups over classical methods but require quantum computers with millions of qubits. Grover's search algorithm, traditionally used for database search, provides a quadratic speedup and is now being explored for factoring bi-primes. The oracle can be built using adder and multiplier circuits utilizing the Quantum Fourier Transform (QFT).

#### Statement

Given a bi-prime number \(N = p \times q\) (where \(p\) and \(q\) are unknown prime numbers), determine the values of \(p\) and \(q\) using Grover’s algorithm. Demonstrate the algorithm for the following list of numbers:

- 35
- 115
- 893 (bonus task)

Use the appropriate number of qubits to store the number \(N\) and outputs \(p\) and \(q\).

## Approach

While there are multiple ways to solve this problem, the fundamental approach remains consistent. Three input registers \(|x⟩, |y⟩, |z⟩\) are required. The register \(|z⟩\) should store the input value \(N\) and should contain \(n = \log_2{N}\) qubits. The registers \(|x⟩, |y⟩\) should be large enough to store the prime factors of \(N\).

The oracle \(U_o(N)\) should be such that for input registers \(|x⟩, |y⟩\):

$$
U_o(N)|x⟩|y⟩ = \begin{cases} 
|x⟩|y⟩ & \text{if } x \times y \neq N\\ 
-|x⟩|y⟩ & \text{if } x \times y = N 
\end{cases}
$$

Now, we implement this oracle into Grover’s circuit and run the circuit multiple times to obtain the amplitudes of registers \(X\) and \(Y\), thereby determining the prime factors.

## Outputs

### N = 35
![Output for N=35](https://github.com/adarshukla3005/Grovers_Algo/assets/153619593/7696f7cf-b905-4435-ae65-37ebdc598f6b)

### N = 115
![Output for N=115](https://github.com/adarshukla3005/Grovers_Algo/assets/153619593/8fc5f5cf-5a45-4645-9124-a03b5102d1f7)

## Implementation Details

### Prerequisites

Ensure you have the following packages installed:

- Python 3.7 or higher
- PennyLane
- NumPy
- Matplotlib

Install the necessary packages using pip:

```sh
pip install pennylane numpy matplotlib
