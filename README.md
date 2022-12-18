# cs4775_final_project
Final project repo for codes and datasets
## Steps
* Step 0: Download the DNA sequences from BOLD system (https://v3.boldsystems.org/index.php/Public_BINSearch?query=zerynthia&searchBIN=Search+BINs) as *.fas files. Collect sampling data from BOLD and generate zerynthia_data.csv, which contains all the other information we need (country, longitude and latitude of the sampling location, and date of sampling. 

* Step 1: Run clustering.ipynb with the *.csv file as input.

  - all_taxa.txt contains all the DNA sequences for species in Zerynthia. Run clustering.ipynb with the *.csv file as input and generate a new intermediate file data_with_newnames.csv, which decorated the sample names with the species name, the geographical cluster the sample belongs to, and the sampling date. Another file, area_xy.txt, will also be generated, which includes the id of the clusters and the center of each cluster. At the same time, all_taxa.txt will be rewrited.

* Step 2: Import all_taxa.txt to MEGA11 and run multiple sequences alignment and generate *.nex file. 

  - There are three different *.nex files: aligned.nex uses underscore "_" as separator, while final_alignment.nex and final_location.nex use slash "/" as separator. Both aligned.nex and final_alignment.nex use numbers as the identifier for the geographical cluster, while final_location.nex uses a string describing the actual geographical range of the cluster.

* Step 3: Run BEAUTi and import *.nex. Partition the datasets based on locations and tune the model. Generate multiple *.xml files. The details for tuning the models were given in the final report.

* Step 4: Run Beast using the *.xml files. 

  - There are multiple files included in the repository: mega_k_mean_trial7.xml partitioned the geographical information into 15 clusters, and was run for a length of 10^7 on Coalescent Bayesian Skyline model and Optimised Relaxed Clock and used tip dates. final_trial_no_1.xml partitioned the geographical information into 7 clusters, and was run for a length of 10^7 on Coalescent Constant Population model and Strict Clock while not using the tip dates. final_trial1.xml, final_trial2.xml, and final_trial3.xml partitioned the geographical information into 7 clusters, and was run for a length of 10^7 on Coalescent Constant Population model and Strict Clock while using the tip dates. dispersal_graph_1.xml partitioned the geographical information into 7 clusters, and was run for a length of 5*10^6 on Coalescent Constant Population model and Strict Clock while using the tip dates. dispersal_graph_1.xml also utilized final_location.nex to describe the geographical information, which was helpful for generating the video of Zerynthia dispersal for later steps. After each chain is run, a *.log file, two *.trees files, as well as some of the other files will be genearated.

* Step 5: Run Tracer using *.log files to check convergence.

* Step 6: Run Treeannotator using *.trees to combine trees into tree, and write to a new *.tree file. The details were given the the final report.

* Step 7: Run logcombiner for *.log files to generate a new *.log file and run Tracer to check convergence again.

* Step 8: Run Figtree to import the *.tree file and visualize the phylogentic tree.

* Step 9: Run Spread3 to generate disperal movie using *.log and *.tree, together with *.json, which includes the geographical information for the map.
