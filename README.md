# mating_loci_Chaetothyriales
HMM profiles to identify the mating loci genes in Chaetothyriales (Fungi: Ascomycota)


These profiles were compiled by downloading from NCBI all genes sequences for the genes APN2,MAT-1-1, MAT-1-1-4, and MAT-1-2 previously identified by 
Teixeira et al. 2017, annotating all the sequences using InterPro v101.0 (Paysan-Lafosse et al. 2022), and correcting any previous missassingment (see the file "Teixeira_et_al_2017_IPRScan_annotations.csv"for more details). Each gene sequences were aligned using MAFFT v7 (Katoh and Standley 2013) and the “E-INS-i” 
strategy (the *.fas files). The resulting alignments were used to build HMM profiles using HMMER v3.3.2 (Eddy 2011). The generated profiles were concatenated in a 
single one, and it were able to correctly identified the genes of Teixeira et al. (2017) that obtained a full sequence scores higher than 100 (see the file "Results_Teixeira_et_al_2017_sequences_HMM_mating_loci_profile.txt").


####################### HOW TO USE THE PROFILE #######################

For using this profile (the file "Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm"), first you will need a working version of HMMER 3 (it can be downloaded at 
http://hmmer.org/). After installing HMMER you can run the profile search with the command below (run with everything in the same folder you are in the terminal (or 
add the paths to the files). As input you will need a fasta file with the protein sequences to be compared with the profile.

hmmsearch --tblout  NAME_YOUR_RESULTS.txt Teixeira_et_al_2017_corrected_MAT_profile_v0.1.hmm YOUR_PROTEINS.fasta 

In "target name" is the sequences titles and "query name" indicates which gene profile has a match for the target. As rule of 
thumb, a a full sequence score over 100 should be a true match, and all Domatiaceae genes identified with a full sequence score above 100 were confirmed by its 
annotation using IPRScan.

 
########################### REFERENCES #############################

Teixeira et al. 2017 doi: 10.1016/j.simyco.2017.01.001

Katoh and Standley 2013 doi: 10.1093/molbev/mst010

Paysan-Lafosse et al. 2022 10.1093/nar/gkac99

Eddy 2011 doi: 10.1371/journal.pcbi.1002195
