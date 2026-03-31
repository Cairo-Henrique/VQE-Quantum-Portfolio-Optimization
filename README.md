# Quantum Portfolio Optimization using VQE

### Knapsack Problem and Portfolio Optimization

This project explores quantum optimization using the Variational Quantum Eigensolver (VQE) applied to two classical optimization problems:

* Knapsack Problem (Combinatorial Optimization)
* Portfolio Optimization (Quantum Finance)

The project was developed during the Brazil Quantum Camp 2026 by team QInvest, achieving 3rd place among 160 participants.

---

# Overview

Near-term quantum computers (NISQ devices) are limited in qubit count and noise levels.
Hybrid algorithms such as Variational Quantum Eigensolver (VQE) provide a promising approach for solving optimization problems under these constraints.

This project investigates the performance of VQE in:

* Combinatorial optimization (Knapsack)
* Financial optimization (Portfolio selection)
* Continuous allocation using Pauli Correlator Encoding (PCE)

---

# Part 1 — VQE for Knapsack Problem

## Problem

The Knapsack Problem is a classical combinatorial optimization problem:

Maximize total value subject to a weight constraint.

This problem was reformulated as:

* QUBO (Quadratic Unconstrained Binary Optimization)
* Ising Hamiltonian
* Solved using VQE

## Methodology

Steps:

1. Convert Knapsack → QUBO
2. Convert QUBO → Ising Hamiltonian
3. Define parameterized quantum circuit (Ansatz)
4. Evaluate expectation value
5. Classical optimization (SPSA)
6. Convergence to minimum energy

## Key Challenges

* QUBO formulation
* Hamiltonian construction
* Ansatz selection
* Optimizer convergence

## Results

* Initial solution: value = 25
* After optimization: Optimal solution = 32

The algorithm successfully converged to the global optimum.

---

# Part 2 — VQE for Portfolio Optimization

## Problem

Portfolio optimization aims to:

* Maximize expected return
* Minimize risk

Based on Modern Portfolio Theory (Markowitz).

This project used:

* 10 stocks from S&P 500
* Historical data (2021–2026)
* Real market data via yfinance

### Selected Assets

* AAPL
* MSFT
* JPM
* XOM
* JNJ
* WMT
* TSLA
* AMZN
* META
* GOOGL

---

# Quantum Formulations

Two quantum approaches were tested:

### 1. Binary Portfolio (QUBO + VQE)

Each asset:

* 1 qubit
* 0 → not selected
* 1 → selected

### 2. Continuous Portfolio (Pauli Correlator Encoding)

* Continuous weights
* Closer to classical Markowitz model
* Extracted from quantum correlations

---

# Benchmark

The quantum results were compared against:

* Classical Monte Carlo Markowitz solution
* S&P 500 Index
* Equal-weights portfolio

---

# Results

### VQE Binary Portfolio

Selected assets:

* GOOGL
* WMT
* XOM
* JPM

Performance:

* 193% of S&P 500 return
* Lower volatility than benchmark
* Best risk-return tradeoff

| Method                   | Risk   | Score  | Performance |
| ------------------------ | ------ | ------ | ----------- |
| VQE Binary               | 0.0234 | 11.178 | Best        |
| Quantum Continuous (PCE) | 0.0294 | 8.422  | Good        |
| S&P 500                  | 0.0247 | 5.582  | Baseline    |

The quantum binary approach achieved the best overall performance.

---

# Technologies

* Python
* Qiskit
* NumPy
* SciPy
* yfinance
* Quantum simulators
* Variational Quantum Algorithms

---

# Algorithms Used

* Variational Quantum Eigensolver (VQE)
* SPSA Optimizer
* TwoLocal Ansatz
* QUBO Formulation
* Pauli Correlator Encoding (PCE)

---

# Future Work

* Run on real quantum hardware (IBM Quantum)
* Increase number of assets
* Add transaction costs
* Improve continuous encoding
* Hyperparameter optimization

---

# References

* Markowitz, H. Portfolio Selection (1952)
* Peruzzo et al. VQE (2014)
* Qiskit Finance Documentation
* Variational Quantum Algorithms (Nature Reviews Physics)

---

# Team

QInvest — Brazil Quantum Camp 2026

* Alexandre Barbosa de Almeida
* Cairo Henrique Vaz Cotrim
* Élen Silva Almeida
* José de Anchieta C C Netto
* Júlio César Reis da Silva
* Leonardo Alves Santana
* Matheus Albert Oliveira dos Santos
* Michel Pereira da Cunha
