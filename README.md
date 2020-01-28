# Methylation-Islands
Find clusters of methylated CpGs within a genome

How it works (Supp Fig 2, Jeong et al. 2018):

"The sliding window approach for identifying methylation islands (MIs). A) The window moves in a 5’ -> 3’ fashion and calculates the mCG fraction of windows until a window meets the mCG fraction threshold (0.02 for this study). B) A window that satisfies the threshold is extended by 50bp a time until the entire region (original window + extension) falls below the threshold. C) The MI is terminated at the last mCG of the previously evaluated region and the evaluation mCG fraction of windows at the next downstream mCG starts."


![MI diagram](https://i.imgur.com/hqkwmSu.png)

Usage of the script:

./methyl_island_sliding_window.pl \<window size> \<mCpG fraction> \<step size> \<sorted mCpG File>
  
  window size - starting size of the methylation island window
  
  mCpG fraction - the minimum fraction of methylated CpGs required within the window to be accepted
  
  step size - base pairs to extend an accepted window by (continues extending by the step size as long as the mCpG fraction is met)
  
  mCpG File - input file with a list of all methylated CpGs in the genome, sorted by scaffold/chromosome and position
