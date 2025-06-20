
---

# README: Maritime Port Connectivity Network Analysis

## Project Overview
This project analyzes the **Maritime Port Connectivity Network** using data from the **Port Liner Shipping Connectivity Index (PLSCI)** and **Liner Shipping Bilateral Connectivity Index (LSBCI)** provided by UNCTAD. The network represents global container port connectivity, capturing both port-level performance and country-level trade links.

The analysis includes:
- Network construction and preprocessing.
- Centrality measures to identify key ports.
- Community detection using modularity analysis.
- Assortativity and clustering coefficient calculations.

## Dataset Description
### Sources
1. **PLSCI**: Port-level connectivity data (e.g., frequency of services, operators, direct connections).
2. **LSBCI**: Country-pair connectivity data (e.g., transshipments, carriers).

### Nodes and Edges
- **Nodes**: Ports (e.g., "Shanghai, China").
- **Edges**: Bilateral maritime connectivity between ports, weighted by the PLSBCI metric.

## Network Construction
### Steps:
1. **Data Cleaning & Preprocessing**:
   - Combined PLSCI and LSBCI datasets.
   - Calculated the weighted metric **PLSBCI** for port pairs.
   - Applied thresholds to retain realistic connections (top 12,749 port pairs).

2. **Adding Coordinates**:
   - Geocoded ports to include latitude and longitude.

3. **Region Classification**:
   - Assigned ports to regions based on geographic coordinates.

4. **Graph Format Conversion**:
   - Exported the network as a `.graphml` file for easy processing.

### Final Network Statistics:
- **Nodes (N)**: 908
- **Edges (E)**: 12,749

## Analysis Tasks
### Task 1: Initial Observations
- Degree distribution analysis revealed a right-skewed, heavy-tailed pattern indicative of a scale-free network with hubs.
- Estimated power-law exponent (γ): 1.8395.

### Task 2: Centrality Measures
Centrality metrics were calculated to identify key ports:
1. **Eigenvector Centrality**: Singapore ranked highest.
2. **Katz Centrality**: Top ports include Singapore, Busan, Shanghai.
3. **Betweenness Centrality**: Singapore leads due to its strategic location.
4. **Closeness Centrality**: Singapore achieved a perfect score of 1.0.
5. **HITS Algorithm**:
   - Authority Score: Shanghai ranked first.
   - Hub Score: Singapore ranked first.

### Task 3: Modularity & Community Detection
- Used the Louvain algorithm for community detection.
- Detected 3 communities with a modularity score of 0.1507 (weak community structure).
- Insights:
  - Community 0 (Red): Major global shipping hubs.
  - Community 1 (Blue): Regional connectors.
  - Community 2 (Green): Peripheral or specialized ports.

### Task 4: Assortativity Analysis
- Degree assortativity coefficient: -0.6889 (disassortative network).
- Indicates a hub-and-spoke structure where high-degree nodes connect to low-degree nodes.

### Task 5: Clustering Coefficients
1. **Global Clustering Coefficient**:
   - Real-world network: 0.0685.
   - Random graph comparison: 0.0302.
2. **Local Clustering Coefficients**:
   - Ports like Antwerp and Rotterdam exhibit higher clustering coefficients due to regional alliances.
   - Local Clustering is usually less for higher-degree nodes.

## Key Insights
1. Strategic hubs like Singapore dominate global shipping networks due to their geographic location and infrastructure.
2. The network exhibits scale-free behavior with disassortative connectivity patterns typical of transportation systems.
3. Weak modularity suggests interconnectedness across communities rather than strong segregation.
4. China’s ports play a crucial role in maritime trade we simulated a targeted disruption of 90% of Chinese ports revealed that alternative ports, such as Colombo in Sri Lanka, rise in relative importance—showing latent strategic potential in the regional network.

