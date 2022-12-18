# cs4775_final_project
* Final project repo for codes and datasets
* Step 1: all_taxa.txt contains all the DNA sequences for species in Zerynthia. zerynthia_data.csv contains all the other information we need. Run clustering.ipynb and generate a new intermediate file data_with_newnames.csv and area_xy.txt. At the same time, all_taxa.txt will be rewrited.
* Step 2: Import all_taxa.txt to MEGAX and run multiple sequences alignment and generate aligned.nex file.
* Step 3: Run BEAUTi and import aligned.nex. Partition the datasets based on locations and tune the model. Generate multiple *.xml files.*
* Step 4: Run Beast.
* Step 5: Run Tracer to check convergence.
* Step 6: Run Treeannotator to combine trees into tree.
* Step 7: Run logcombiner and run Tracer to checl convergence again.
* Step 8: Run Figtree to generate the phylogentic tree.
* Step 9: Run Spread3 to generate disperal movie.
