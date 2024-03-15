# Python Implementation of Schelling's Model of Segregation

This Python script implements Schelling's Model of Segregation, simulating the spatial segregation of agents on a grid based on a similarity threshold. It iteratively moves dissatisfied agents to improve satisfaction and minimize dissimilarity. Users can customize parameters like the similarity threshold and maximum iterations to observe the emergence of segregated clusters. The script supports command-line arguments for input data grid, threshold, and iterations, providing insights into the dynamics of segregation and the influence of different factors on the resulting patterns.


## Dependencies

The script requires the following dependencies:
- Python 3.x
- NumPy
- ArgumentParser
- datetime


## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install the libraries/modules mentioned above.

```bash
pip install NumPy
pip install ArgumentParser
pip install datetime
```


## Function Definitions

The script includes several function definitions that handle different aspects of the simulation, such as loading the grid, computing similarity, and simulating the model. Here's a brief overview of the functions:
- `get_parser()`: Parses the command-line arguments.
- `load_grid(filename)`: Loads the data grid from a file.
- `print_model(grid)`: Prints the data grid.
- `compute_index_of_dissimilarity(grid, subregion_grid)`: Computes the index of dissimilarity.
- `get_empty_cells(grid)`: Returns a list of empty cell positions in the grid.
- `get_agents(grid)`: Returns a dictionary of agent positions and types.
- `get_neighbors(grid, agents)`: Returns a dictionary of agent positions and their neighboring positions and types.
- `compute_similarity(agents, neighbors)`: Computes the similarity between agents and their neighbors.
- `compute_satisfaction(similarity, sim_threshold)`: Computes the satisfaction level of agents based on the similarity threshold.
- `simulate_model(grid, sim_threshold, max_iterations)`: Simulates the Schelling segregation model.
- `process_start()`: Processes the command-line arguments and executes the simulation.


## Command-line Options:

The command-line options are used to customize the simulation of Schelling's Model of Segregation. The options are parsed as follows:

- `-dg` or `data_grid` (default: "data/schelling.txt"): Specifies the path to the file containing the data grid, which represents the initial configuration of agents.
- `-dsr` or `data_subregion`: Path to the file containing the subregion of the data grid.
- `-st` or `sim_threshold`: Desired similarity level with nearby neighbors (float).
- `-mi` or `max_iterations`: Maximum number of iterations to simulate the segregation (integer).

In the commandline, the arguments are being handled through `-dg` `-dsr` `-st` and `-mi`

In the script, these will be parsed through the following `data_grid` `data_subregion` `sim_threshold` and `max_iterations` respectively


## Usage

Run the script `schellings_test.py` with the following command:

```bash
python schellings_test.py -dsr <data_subregion> -st <sim_threshold> -mi <max_iterations>
```
Here's an example command to run the script:
```bash
python schellings_test.py -dsr data/schelling4.txt -st 0.35 -mi 100 > logs/testrun_202307100404.txt
```
This command simulates the Schelling segregation model using the `data/schelling.txt` data grid as default and `data/schelling4.txt` as the sub-region data grid, a similarity threshold of 0.35, and a maximum of 100 iterations. The output is redirected to the `logs/testrun_202307100404.txt` file, where the logs directory is within the same root as the `schellings_test.py` script.


## Main Script
The main script handles the execution flow of the program. It parses the command-line arguments, loads the data grid, computes the index of dissimilarity, and performs the simulation. It also prints the results and logs the output.


## References
Model Explanation: [Martin Hilbert's Schelling's Segregation Model Explanation](https://www.youtube.com/watch?v=AZlWOykGzYg)

Index of Dissimilarity Calculation: [Measuring Residential Segregation Page 5](https://economics.yale.edu/sites/default/files/segregation-measures_03-24-14.pdf)
