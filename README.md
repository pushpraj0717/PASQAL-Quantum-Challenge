# Quantum-AI for Renewable Energy Distribution in Prosumer Grids

Conceptual proposal for the **Blaise Pascal Quantum Challenge (PASQAL), Call for Ideas** 

> **Status:** concept-stage proposal. No code was run on quantum hardware or simulators, and the figures are illustrative. See [Scope and limitations](#scope-and-limitations).

## Problem

Rooftop solar and home storage turn households into *prosumers* (they both produce and consume electricity). As prosumer numbers grow, grids have to balance many small, fluctuating sources, and smart-meter (AMI) data produces large, interconnected graphs. The question we asked: could quantum optimisation plus ML forecasting help allocate surplus renewable energy to demand more efficiently?

The proposal addresses the challenge of integrating renewables into modern grids and maps to **UN SDG 7** (affordable, reliable, sustainable energy).

## Proposed approach

1. **Forecasting layer (classical ML):** LSTM for long-term demand/generation trends, ARIMA for short-term fluctuations, autoencoders for anomaly detection in consumption patterns.
2. **Optimisation layer (quantum):** model the grid as a graph (nodes = prosumers, substations, transformers; edges = energy flow) and minimise transmission losses while balancing supply and demand, using QAOA-based graph optimisation, with Pasqal's neutral-atom platform as the target hardware.
3. **Feedback:** optimised flows inform resource allocation and maintenance decisions.

Formulation: minimise Σ c<sub>ij</sub> x<sub>ij</sub> over grid edges, where c<sub>ij</sub> is the loss/cost on edge (i, j) and x<sub>ij</sub> the flow, under a linear power-flow simplification.

## Sustainability impact assessment (my main section)

- Alignment with SDG 7 and the environmental, social and economic arguments for prosumer-based grids
- Scalability from community microgrids to national networks
- Proposed KPIs: energy efficiency gains, carbon footprint reduction, cost savings, renewable utilisation, optimisation time savings, grid stability

## My contribution

- Led the **literature review** and the **sustainability impact assessment**
- Contributed to the technical formulation and innovation sections

## Scope and limitations

- This is a design-stage proposal, not an implementation. There are no benchmarks or hardware results.
- The scaling comparison in the appendix (classical algorithms vs. QAOA) is a back-of-envelope illustration. It is **not** evidence of a demonstrated quantum speedup, and QAOA has no proven advantage for this problem class.
- With linear flow constraints the objective is a linear program, which is classically tractable. Hard combinatorial structure would enter through discrete decisions (e.g. switching, storage dispatch, topology), which a full formulation would need to model explicitly.
- Next steps would be: formulate a concrete QUBO/Ising instance, simulate small grids, and benchmark against classical solvers.

## Key references

- Farhi, Goldstone, Gutmann (2014). *A Quantum Approximate Optimization Algorithm.* [arXiv:1411.4028](https://arxiv.org/abs/1411.4028)
- Blenninger et al. (2024). *Q-GRID: Quantum Optimization for the Future Energy Grid.* KI – Künstliche Intelligenz
- [add remaining references after verifying each one]

## Repository contents

- `README.md`: this summary
- `docs/`: [full submission PDF]
