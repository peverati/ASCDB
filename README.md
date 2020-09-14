          _       ______     ______  ______   ______    
         / \    .' ____ \  .' ___  ||_   _ `.|_   _ \   
        / _ \   | (___ \_|/ .'   \_|  | | `. \ | |_) |  
       / ___ \   _.____`. | |         | |  | | |  __'.  
     _/ /   \ \_| \____) |\ `.___.'\ _| |_.' /_| |__) | 
    |____| |____|\______.' `.____ .'|______.'|_______/  


# ASCDB: A Small(er) Chemistry Database.

A statistically significant database with a broad computational chemistry purpose.

Morgante, P.; Peverati, R.; “Statistically representative databases for density functional theory via data science” Phys. Chem. Chem. Phys. 2019, 21, 19092-19103. [![DOI:10.1039/C9CP03211H](https://img.shields.io/badge/DOI-10.1039/C9CP03211H-990033)](https://doi.org/10.1039/C9CP03211H)

ASCDB is a statistically significant database created  from the three largest computational chemistry databases: [GMTKN55](https://www.chemie.uni-bonn.de/pctc/mulliken-center/software/GMTKN/gmtkn55) by the Grimme and Goerigk groups, [MGCDB84](https://www.tandfonline.com/doi/full/10.1080/00268976.2017.1333644) by Mardirossian and Head-Gordon, and [Minnesota 2015B](https://comp.chem.umn.edu/db2015/) by the Truhlar group. Our group recently collected them in the [ACCDB](https://github.com/peverati/ACCDB) collection of databases. 

ASCDB was created as a tool for the evaluation and parametrization of electronic structure theory methods (both DFT and semi-empirical methods), but it can be useful in other areas (benchmarking of DFT or basis sets, data analysis, etc.) Using statistical methods, we reduced the number of energy data points of ACCDB from 6,953 to 200, requiring a total of 350 single-point calculations. After statistical analysis, we identified and labelled 16 groups of chemical environments in four areas of chemistry: Non-Covalent interactions (group 1), Thermochemistry (group 2), Non-local effects (group 3), Unbiased calculations (group 4). 

## The current version of ASCDB has 16  groups of properties:

- **Non-Covalent**: A (NCA15)

- **Non-Covalent**: B (NCB21)

- **Non-Covalent**: Cluster (NCC21)

- **Non-Covalent**: Water (NCW3)

- **Thermochemistry**: Atomization and Reaction Energies (TARE19)

- **Thermochemistry**: Barrier Heights A (TBHA20)

- **Thermochemistry**: Barrier Heights B (TBHB16)

- **Thermochemistry**: Hydrocarbons Reactions (THR5)

- **Non-Local Effects**: Mixed A (NLMA15)

- **Non-Local Effects**: Mixed B (NLMB7)

- **Non-Local Effects**: Multi-Reference (NLMR11)

- **Non-Local Effects**: Self-Interaction Error (NLSIE9)

- **Unbiased Calculations**: Mindless Benchmarks A (UMBA8) 

- **Unbiased Calculations**: Mindless Benchmarks B (UMBB5)

- **Unbiased Calculations**: Mindless Benchmarks C (UMBC7)

- **Unbiased Calculations**: Atomic Energies per Electron (UAE18)

## Structure.

This repository has the following directories:

- **Automation**: Containing all snakemake file to automate calculations.
- **Evaluation**: Containing all the reference data in .csv format (ASCDB.csv), an Excel file formatted in a "ready-to-use" fashion (ASCDB.xlsx).
- **Geometries**: Containing all geometries for single-point energy calculations, in xyz file format (including charge and spin multiplicity).

ASCDB contains 350 geometry files in xyz format, which result in 200 datapoints. If one desires, regression formulas are provided to calculate the Mean Unsigned Errors for the parent databases (GMTKN55, MGCDB84, MN2015B) using the MUE of the datapoints in ASCDB. This is provided in the Excel file (ASCDB.xlsx).

The reference energies for each database or set are reported in three equivalent csv files named ASCDB_*.csv. The reference energies are reported in kcal/mol, kJ/mol or Hartrees. In general, reference values have been obtained with high-level theoretical calculations, and we recommend referring to the original publications for details. Each csv file also includes the stoichiometry coefficients and reference to the corresponding filename in the Geometries directory for each unique reference data point, and can be easily parsed for calculation of statistics.

## Automation

Automation of the jobs and calculation of the statistics is achieved through snakemake workflows. Refer to the README in the **Automation** directory for detailed instructions on how to use it, modify it, and extend it.

## How to cite:

This work is published under GNU-GPL license and credit must be given to the authors of the original material, as appropriate. Everything in ASCDB is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

**Citations for published scientific material:**

If you are using ASCDB, or any of the automation scripts you should cite the ASCDB database (see below), **and** the snakemake original article.

*The reference for the ASCDB database is*:

Morgante, P.; Peverati, R.; *Phys. Chem. Chem. Phys.*, **2019**, 21, 19092–19103. You can find it [here](https://pubs.rsc.org/en/content/articlelanding/2019/cp/c9cp03211h#!divAbstract).
