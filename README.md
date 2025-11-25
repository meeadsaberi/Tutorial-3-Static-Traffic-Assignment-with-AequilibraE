# Tutorial #3: Static Traffic Assignment in Python using AequilibraE: Sioux Falls and Gold Coast Networks

Perform static traffic assignment on the Sioux Falls and Gold Coast road networks using the open-source AequilibraE library. This hands-on tutorial guides you through the complete workflow, from reading TNTP-format network and demand data to building the graph, running a Frank–Wolfe assignment, and visualizing results such as link volumes and V/C ratios.

The workflow is fully Python-based and Colab-ready for lightweight and reproducible transport modelling.

Sioux Falls network example:
https://colab.research.google.com/drive/1zU-61rYj4_vE9ActZIq6gwh_KTX5YeZ8  
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1zU-61rYj4_vE9ActZIq6gwh_KTX5YeZ8)

Gold Coast network example
https://colab.research.google.com/drive/1F5f5S3s1OnZW-T-F80OMRsYF2oDSPYUq  
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1F5f5S3s1OnZW-T-F80OMRsYF2oDSPYUq)

## What this notebook does
- Installs and configures AequilibraE with compatible NumPy version (1.26.4).
- Loads Sioux Falls and Gold Coast TNTP networks, OD demand, and node coordinates from the [Transportation Networks repository](https://github.com/bstabler/TransportationNetworks).
- Cleans and validates network consistency (nodes, links, and geometry).
- Builds a Graph and Aequilibrae Matrix directly in Python.
- Runs static traffic assignment using the Frank–Wolfe algorithm (also supports All-or-Nothing, MSA, BFW, etc.).
- Visualises:
  - Network topology (links and nodes)
  - Convergence curve (relative gap vs iterations)
  - Traffic volumes (line width or colour scaled by flow)
  - Volume-to-Capacity (V/C) ratios for congestion mapping
 
## Quick start (Colab)
1. Click the Open in Colab link or badge above.
2. Run the first install cell to set up AequilibraE and dependencies.
3. The notebook then guides you to download the network and demand files from GitHub.
4. Run all cells to:
   - Build the network
   - Run traffic assignment
   - View convergence and flow maps

## Files
- Tutorial_3_Static_Traffic_Assignment_in_Python_using_AequilibraE_Gold_Coast.ipynb — main notebook

## Data
The notebook reads open data directly from the Transportation Networks repository:
https://github.com/bstabler/TransportationNetworks/tree/master/GoldCoast
and
https://github.com/bstabler/TransportationNetworks/tree/master/SiouxFalls

- SiouxFalls_net.tntp — network links with capacities and travel times
- SiouxFalls_node.tntp — node coordinates (longitude, latitude)
- SiouxFalls_trips.tntp — OD matrix in flat TNTP format

- Goldcoast_network_2016_01.tntp — network links with capacities and travel times
- Goldcoast_nodes_2016_01.tntp — node coordinates (longitude, latitude)
- Goldcoast_trips_2016_01.tntp — OD matrix in flat TNTP format

## Example outputs
- Network map (links and nodes)
- Convergence chart (Frank–Wolfe algorithm)
- Flow visualisations (line width ~ volume; colour ~ flow or V/C ratio)

## Next steps
Once you’ve completed the base tutorial, try:
- Switching assignment algorithms (MSA, BFW, CFW)
- Generating skimming matrices for accessibility analysis
- Exporting results to GIS (GeoJSON, shapefiles)
- Scaling up to larger or real-world networks

For more examples, visit the AequilibraE documentation:
https://www.aequilibrae.com/latest/python/index.html

Developed by: Meead Saberi, UNSW Sydney
