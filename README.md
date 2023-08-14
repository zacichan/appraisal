# MONTE CARLO METHODOLOGY FOR COST BENEFIT ANALYSIS
This script provides a Monte Carlo methodology for conducting cost-benefit analyses for projects. It models project costs using different distribution assumptions and calculates cost distributions based on user-specified low and high estimates. The script focuses on four main distribution assumptions: Uniform, Normal (without central), Normal (with central), and Log-Normal distributions. The purpose of this script is to aid in understanding the uncertainty associated with project cost estimates and to provide tools for analyzing cost distributions.

## Packages
This script requires the following R packages to be installed and loaded:

- `beisics`: A custom package for theme settings.
- `readxl`: For reading Excel files.
- `tidyverse`: For data manipulation and visualization.

## Data
The script generates a synthetic dataset with 100 rows and 3 columns: project_id, low, central, and high. The low, central, and high columns represent different cost estimates for each project.

## Set Seed
To ensure reproducibility, the script sets a seed value using set.seed(123).

## Distribution Functions
The script defines functions to create different distributions based on the specified parameters. Each function generates possible cost values for projects based on the low and high estimates and applies a probability distribution function. The resulting distribution is sampled using the sample() function to simulate different cost scenarios.

Four main distribution assumptions are covered in the script:

- **Uniform Distribution**: Projects' costs are modeled using a uniform distribution spanning from the low to high estimates.

- **Normal Distribution (without central)**: Projects' costs are modeled using a normal distribution with mean calculated as the midpoint between high and low estimates and standard deviation as a quarter of the distance between them.

- **Normal Distribution (with central)**: Similar to the previous assumption, but the mean of the normal distribution is assumed to be the central value.

- **Log-Normal Distribution**: The log-normal distribution allows for a right skew and is determined by estimating parameters such as mean and standard deviation from the central estimate.

## Credible Intervals
The script calculates the highest density interval (HDI) for each distribution assumption. HDIs are used to characterize uncertainty and provide credible intervals for cost estimates. This is done using the bayestestR package.

## Plotting
The script generates density plots to visualize the cost distributions for each distribution assumption. It also aggregates the cost data from different assumptions and plots them together to compare the distribution shapes.

Please note that this script assumes the availability of the beisics package for theme settings and might require additional data processing or adjustments based on specific use cases.
