# Smart AI-Based Traffic Management System

This repository contains the codebase for N-Coders' solution to **Smart India Hackathon 2024** Problem Statement SIH 1607, which involves developing a **smart AI-based solution for traffic management on routes with heavy traffic**. Our solution leverages **real-time monitoring** and dynamically adapts **traffic light timings** to reduce congestion and improve efficiency across intersections.

## Project Overview

- **Problem Statement ID**: SIH 1607
- **Project Theme**: Smart Automation
- **Team Name**: N-Coders
- **Team ID**: 30206

### Solution Highlights
Our solution integrates **Multi-Agent Proximal Policy Optimization (MAPPO)** and **Graph Attention Network (GAT)** for coordinated traffic management. This combination provides both **local adaptability** at each intersection and **global optimization** across the network.

### Core Technologies
- **MAPPO**: Multi-Agent Proximal Policy Optimization to handle multi-agent reinforcement learning for traffic signals.
- **GAT**: Graph Attention Network to process intersection dependencies and state representations for enhanced decision-making.
- **YOLO**: Real-time object detection model fine-tuned to detect vehicles and pedestrians, enabling real-time traffic data input.

### Key Components
1. **Intersection Representation**: Each intersection is modeled as an independent agent with its own policy network, and a centralized critic evaluates the global traffic state.
2. **Traffic Data Processing**: YOLO detects vehicles and pedestrians, with data mapped to lanes using a homography matrix and 3D spatial transformations.
3. **Reward Mechanism**: Agents are rewarded for reducing local queue length and wait times while the global objective is to maximize throughput and balance loads across intersections.
4. **Non-Conflict Management**: The **Welch-Powell algorithm** (chromatic numbering) handles non-conflicting transits to ensure smooth traffic flow.

## Technical Approach

1. **Real-Time Adaptation**: Continuous updates based on YOLO and GPS data adjust to dynamic traffic patterns.
2. **Centralized Critic with Decentralized Execution**: The centralized critic uses global traffic information, while local policies allow agents to act independently.
3. **Emergency Response and Obstruction Handling**: Overrides for emergency vehicles and obstacle mapping in 3D for managing stray animals and jaywalkers.

### Libraries & Tools
- **Machine Learning**: `torch-geometric`, `torch-RL`, `Cityflow-gym`, `stable-baselines3`
- **Data Sources**: Traffic camera data, maps API, car chip data, `OSMnx` for road graph generation.

## Feasibility and Viability

This model is designed for **scalability** and **adaptability** to various infrastructure levels, including intersections without traffic cameras, using GPS for monitoring. The **centralized training and decentralized execution** model allows real-time adaptability and optimization.

## Benefits

- **Traffic Congestion Reduction**: Optimization of traffic lights and efficient route management.
- **Environmental Impact**: Reduction in emissions and fuel consumption.
- **Emergency and Safety Features**: Prioritizes emergency vehicles and dynamically manages obstructions.
- **Continuous Learning**: System adapts to changing traffic patterns, construction, and population shifts for long-term efficiency.

## Research and References
- [Proximal Policy Optimization](https://arxiv.org/abs/1707.06347)
- [Multi-agent PPO](https://arxiv.org/abs/2103.01955)
- [Graph Attention Networks](https://arxiv.org/abs/1710.10903)
- [Realtime Lane-wise Car Assignment](https://arxiv.org/abs/2404.15212)
- [Spatial Coordinate Transformation](https://pubmed.ncbi.nlm.nih.gov/33202659/)
- [Cityflow for Traffic Simulation](https://arxiv.org/abs/1905.05217)
- [Welch-Powell Algorithm for Traffic Routing](https://www.researchgate.net/publication/381494184)

