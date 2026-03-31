# Bits and Qubits - New Attributes of Basic Information Carriers

## Classical Bit vs Qubit

### Classical Bit
- A classical bit is either **0** or **1** -- always a definite state.
- Think of a ball sitting at the bottom of one of two valleys. It's clearly in the left valley (0) or the right valley (1). No ambiguity.

### Qubit - The Quantum Twist
- A qubit can be in a **superposition** of 0 and 1 at the same time.
- Written as: **|0> + |1>** (a combination of both states).

---

## The Tunneling Experiment (from the diagram)

Imagine a particle (like an electron) sitting in a double-well potential -- two valleys separated by a hill.

### Step 1: The "Random-Looking" State
- If you measure the particle, you get **50% chance of "0"** and **50% chance of "1"**.
- This *looks* random, but it's NOT truly random.

### Step 2: Why It's Not Random
- The particle is in a **definite quantum state** -- a superposition |0> + |1>.
- This is because of the **wave nature** of the electron. It exists as a wave spread across both wells simultaneously.

### Step 3: Proof It's Not Random -- Tunnel Again
- If it were truly random, tunneling again would keep it random.
- But if you let tunneling happen a second time, the particle ends up in a **definite state "1"**.
- This proves the first state was a precise superposition, not randomness.

---

## Key Takeaway

| Property | Classical Bit | Qubit |
|----------|--------------|-------|
| States | 0 or 1 (one at a time) | |0>, |1>, or any superposition |0> + |1> |
| Measurement | Always gives the same answer | Gives 0 or 1 probabilistically |
| Nature | Definite, like a coin showing heads or tails | Wave-like, exists in both states until measured |

---

## Simple Analogy

Think of a **coin**:
- **Classical bit** = a coin lying flat on a table. It's heads or tails. Period.
- **Qubit** = a coin spinning in the air. It's *both* heads and tails at the same time. Only when you catch it (measure it) does it "choose" one.

But here's the crucial point: **the spinning coin is not "random"** -- it follows precise physical laws. If you know exactly how it's spinning, you can predict what happens next (like the second tunneling producing a definite "1").

---

## Why This Matters

Superposition is the foundation of quantum computing. Because a qubit can be in both states simultaneously, quantum computers can explore many possibilities at once -- this is where their power comes from.


## DiVincenzo 5 core criteria

The DiVincenzo criteria (proposed by David DiVincenzo in 2000) are    
  five requirements for building a practical quantum computer:
                                                                        
  1. A scalable physical system with well-characterized qubits          
  2. Ability to initialize qubits to a known fiducial state             
  3. Long decoherence times (much longer than gate operation times)     
  4. A universal set of quantum gates                                   
  5. A qubit-specific measurement capability 