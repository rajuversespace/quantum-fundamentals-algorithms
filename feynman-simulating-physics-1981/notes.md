# Feynman's "Simulating Physics with Computers" (1981) - Study Notes

> Richard P. Feynman, Keynote Speech at MIT Physics of Computation Conference
> Published in International Journal of Theoretical Physics, Vol. 21, 1982

---

## The Big Question

**Can we simulate physics using computers?**

Not approximately (like numerical methods) -- Feynman wants an *exact* simulation where the computer does exactly what nature does.

---

## Section 1: Introduction - Setting the Rules

Feynman sets up his "game rules":

1. The computer should be **locally connected** (like cellular automata -- each element only talks to its neighbors)
2. The number of computer elements needed should be **proportional** to the space-time volume being simulated (no exponential blowup allowed)
3. Space and time might need to be **discrete** (not continuous) -- which is fine because we can't measure below ~10^-27 seconds anyway

### Key Insight
> If exact simulation requires everything in a finite volume to be analyzable with finite logical operations, and current physics allows infinitely small distances... then either the simulation approach is wrong, or **physical law needs modification**.

---

## Section 2: Simulating Time

Two approaches:
- **Imitate time**: Computer steps through states one-by-one (like cellular automata). Time isn't simulated, it's just... used.
- **Simulate time**: Lay out ALL space-time points at once (a "space-time view"). Each point's state depends on its neighbors.

### The Interesting Twist
What if a point's state depends on **future** points too, not just past ones? Physics actually uses this idea (e.g., positrons as electrons going backwards in time). Computing such a thing is much harder -- it's like solving a boundary value problem instead of just stepping forward.

### Classical Physics Result
Classical physics is **local, causal, and reversible** -- all good properties for computer simulation. No fundamental problems here.

---

## Section 3: Simulating Probability

Here's where things get interesting. Quantum mechanics gives us **probabilities**, not certainties.

### The Exponential Problem

For R particles, you need to describe the probability as a function of ALL their positions: P(x1, x2, ..., xR, t)

- If there are N points in space, you need **N^R configurations**
- That's an **exponential explosion** -- violates Feynman's rules!

### Solution Attempt: Probabilistic Computer

Instead of *computing* probabilities, use a computer that itself *behaves* probabilistically:

- Run the simulation many times
- The frequency of outcomes should match nature's probabilities
- Like how we learn probabilities in nature -- by repeating experiments

### Nice Property of Probabilistic Simulation
To find out what happens in a local region, you just **ignore everything else**. No extra computation needed -- just like in real physics!

---

## Section 4: Quantum Computers - The Side Remark

> This is the section where Feynman essentially **proposes quantum computing**.

### The Idea
Since classical computers can't efficiently simulate quantum systems, **build the computer itself out of quantum mechanical elements**.

- Not a Turing machine -- a machine of a different kind
- Lattice of spins (quantum two-state systems) can imitate field theories
- Each point has two base states: **occupied** or **unoccupied**

### Operators for Each Point

| Operator | What it does |
|----------|-------------|
| a (annihilate) | Occupied -> Unoccupied |
| a* (create) | Unoccupied -> Occupied |
| n (number) | "Is something there?" Returns 1 if yes, 0 if no |
| I (identity) | Does nothing |

These are equivalent to the **Pauli spin matrices** (sigma_x, sigma_y, sigma_z) -- the language of spin-1/2 systems.

### The Open Question (in 1981)
Can every quantum system be simulated by a lattice of spin-1/2 systems? Feynman was confident for **Bose particles** but unsure about **Fermi particles**.

---

## Section 5: Can Classical Computers Simulate Quantum Systems?

**Short answer: NO.** (This is the hidden-variable problem.)

### The Density Matrix Approach

Instead of the wave function, use the **density matrix**:

```
rho(x, x') = psi*(x') * psi(x)
```

- Has TWO coordinates (x and x') per particle -- analogous to position and velocity in classical mechanics
- Has mathematical properties similar to probability

### The Wigner Function

A rewriting of the density matrix as W(x, p) -- a "probability" (in quotes!) for position x and momentum p:

- Integrating over p gives the real probability of position x
- Integrating over x gives the real probability of momentum p
- Looks like a joint probability... but it's NOT quite one

---

## Section 6: Negative Probabilities - THE Problem

### The Core Difficulty

The Wigner function / "probability" **can be negative**.

Example for a single spin:
```
f++ = 0.6    f+- = -0.1
f-+ = 0.3    f-- = 0.2
```

All the *physical* probabilities you compute from these are perfectly positive:
- P(first index +) = 0.6 + (-0.1) = 0.5  (fine!)
- P(first index -) = 0.3 + 0.2 = 0.5  (fine!)
- P(second index +) = 0.6 + 0.3 = 0.9  (fine!)

**But the underlying f values can be negative!**

> "The only difference between a probabilistic classical world and the equations of the quantum world is that somehow or other it appears as if the probabilities would have to go negative."

A classical probabilistic computer can't simulate negative probabilities. That's the fundamental barrier.

---

## Section 7 & 8: The EPR Experiment - Proving It's Impossible

Feynman uses **photon polarization** to make the impossibility concrete.

### The Setup
- An atom emits two photons in opposite directions
- Each photon passes through a calcite crystal (which splits it into Ordinary or Extraordinary rays)
- The crystals are set at angles phi_1 and phi_2

### Quantum Prediction
- P(both Ordinary) = 1/2 * cos^2(phi_2 - phi_1)
- P(both Extraordinary) = 1/2 * cos^2(phi_2 - phi_1)
- P(one O, one E) = 1/2 * sin^2(phi_2 - phi_1)

### The Killer Result

If you set the angle difference to 30 degrees:

| | Classical Maximum | Quantum Mechanics |
|---|---|---|
| P(match) | **2/3** (~66.7%) | **3/4** (75%) |

Quantum mechanics predicts (and experiments confirm!) a **higher correlation** than any classical local model can produce.

### Why Classical Fails (The Bell Argument)

1. Since you can perfectly predict my result from your measurement (when angles match), the outcomes must be **predetermined**
2. Each photon carries a hidden "instruction set" for what to do at each angle
3. At 90 degrees apart, the instructions must be opposite (O becomes E)
4. Working through all possible instruction sets, the maximum match probability at 30 degrees is **2/3**
5. But quantum mechanics gives **3/4** -- and experiments confirm this!

> "It seems almost ridiculous that you can squeeze it to a numerical question that one thing is bigger than another."

---

## Section 9: Discussion - Feynman's Conclusions

### What Feynman Was Really Saying

1. **Nature is quantum, not classical.** Any simulation of nature must be quantum mechanical.
2. Classical computers face a **fundamental** barrier (not just a practical one) in simulating quantum systems.
3. **Quantum computers** -- machines built from quantum elements -- could potentially simulate any quantum system.
4. The relationship between computation and physics runs **both ways**: physics constrains computation, but thinking about computation reveals new physics.

### Famous Quote
> "Nature isn't classical, dammit, and if you want to make a simulation of nature, you'd better make it quantum mechanical, and by golly it's a wonderful problem, because it doesn't look so easy."

---

## Simple Summary - The Paper in 5 Points

1. **Classical physics** can be simulated on a computer -- no fundamental problem.
2. **Quantum physics** requires tracking exponentially many configurations -- classical computers can't keep up.
3. **Probabilistic computers** (classical but random) still can't do it because quantum mechanics needs **negative probabilities**.
4. The **EPR/Bell experiment** proves this isn't just a math trick -- nature genuinely can't be explained by local classical models (2/3 vs 3/4).
5. The solution: build computers from **quantum mechanical parts** -- what we now call **quantum computers**.

---

## Why This Paper Matters

This 1981 talk is considered the **birth of quantum computing** as a field. Feynman didn't just say "quantum computers would be cool" -- he gave a rigorous argument for **why they're necessary**. Classical computers are fundamentally incapable of efficiently simulating quantum physics, so we need a new kind of machine. This insight launched decades of research that continues today.
