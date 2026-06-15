# GATEWAY: A Game-Theory Model for Analyzing Road Tolls and Commuter Response

GATEWAY models how a policymaker setting a road toll and commuters choosing a
travel mode interact, and solves for the resulting equilibrium. It estimates
travel demand, revenue, and consumer surplus as a function of the toll, and
identifies the toll that best meets a stated policy objective.

This repository contains the implementation accompanying our paper:

> H. Wu, Z. Dong, and R. Rojas-Cessa, "GATEWAY: A Game Theory Model for
> Analyzing NYC Road Tolls and Commuter Response," *IEEE Transactions on
> Intelligent Transportation Systems*, 2026. DOI: 10.1109/TITS.2026.3689516

## What it does

- Models commuter travel-mode choice with a **multinomial logit** discrete-choice model.
- Frames the policymaker–commuter interaction as a **Stackelberg game** and solves
  for the **Nash equilibrium**.
- Estimates **revenue** and **consumer surplus** as functions of the toll and finds
  the revenue-maximizing and surplus-maximizing tolls.
- Validated against real-world MTA data across two case studies (2010 toll increase
  and 2025 NYC congestion pricing); predicted a 14% car-demand reduction versus the
  12% reported.

## How it works

1. **Data processing** – cleans and prepares travel-survey data (trip purpose,
   mode, duration, cost).
2. **Logit coefficient estimation** – estimates utility-function coefficients by
   maximum likelihood (via the Biogeme library).
3. **Game solver** – finds the equilibrium toll and travel demand by optimizing the
   policymaker's objective subject to commuter best-response, with O(N) complexity.
4. **Outputs** – optimal toll, estimated demand, revenue, consumer surplus, and
   travel-time effects.

## Getting started

```bash
git clone https://github.com/YOUR_USERNAME/GATEWAY.git
cd GATEWAY
pip install -r requirements.txt
python src/[main_script].py
```

## Data

This project uses public travel surveys (e.g., the NYC Citywide Mobility Survey and
the Regional Household Travel Survey) and MTA traffic data. Raw datasets are not
redistributed here; see the paper for sources and access links.

## Citation

If you use this code, please cite the paper above.

## Acknowledgment

This work was partially supported by the U.S. National Science Foundation under
Grant Award 1856032.

## Authors

Hailun (Helen) Wu, Ziqian Dong, Roberto Rojas-Cessa
