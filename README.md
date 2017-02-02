# RWR-H and RWR-MH

There are three different elements in this repository: 

1. **/Scripts_and_Files Folder**: It contains the scripts and the files used to obtain the results shown in the article: "Random Walk with Restart on Multiplex and Heterogeneous Biological Networks". 

2. **/RWR-M.zip**: It contains all the files and scripts needed to perform a random walk with restart on a multiplex network (RWR-M) such as described in the article: "Random Walk with Restart on Multiplex and Heterogeneous Biological Networks".

3. **/RWR-MH.zip:** It contains all the files and scripts needed to perform a random walk with restart on a multiplex and heterogeneous network (RWR-MH) such as described in the article: "Random Walk with Restart on Multiplex and Heterogeneous Biological Networks".

## RWR-H 

Random walk with restart on a biological multiplex network integrated by 3 layers accounting for different types of links among proteins (PPI, pathways and co-expression). The user provides an initial protein or set of proteins, seed nodes, and the algorithm will measure the proximity of every protein within the network to the input seeds. 

### Installation

All the scripts and files needed to run the algorithm can be obtained by download the compressed file [/RWR-M.zip] (https://github.com/alberto-valdeolivas/RWR-MH/blob/master/RWR-M.zip). Extract the file in the desired location within your computer. The scripts are written in R with some functions developped in C++. Therefore, in order to execute it you need to install [R] (https://cran.r-project.org/doc/manuals/r-release/R-admin.html). 

### Usage

Once the compressed file is extracted, you should move to this folder. The main script is called RWR-M.R and if you open it you can find a detailed explanation of the process along with instructions about how to execute it, the input required files and the output files that will be created. A case example with all the required files is provided. To run the algorithm, you need to type in the command line the following order: 

`Rscript RWR-M.R Input_Files/Seeds_Example.txt Input_Files/Parameters_Example.txt Results_Example`

1. **Input_Files/Seeds_Example.txt**: first argument makes reference to the seed proteins. It should be a plain text file containing the seeds proteins (One protein per line and at least one protein). In the provided example TP53 and LMNB1 genes will be took as seeds. To use your own seeds you can either modify this file or reference here to another plain text file. 

2. **Input_Files/Parameters_Example.txt**: second entry refers to the different parameters of the RWR-M. It should be a plain text file containing the parameters as specified in the example file provided. We strongly recommend to use this file and just modify the numerical values if you want to tune the parameters. The original example file accounts for their default values used in our article. These default values have shown to be very suitable for the method.

3. **Results_Example**: third argument indicates the name you want to provide to the output files. The output files will be generated in the Output_Files folder with the name provided by the user in this argument. Two files with the same name but different extension will be created. The first one is a .txt file containing all the genes in the network and their associated score. The file is sorted by score in such a way that the closer genes to the seeds are located in the top positions. The second file is a .gr network file. It accounts for all the interactions among the seeds and the top k retrieved genes (k is a parameter that we can change in the previous file). This file can be loaded for instance into [Cytoscape](http://www.cytoscape.org/) providing a suitable view of the RWR-M results. 



