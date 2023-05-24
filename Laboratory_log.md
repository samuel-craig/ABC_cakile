# Laboratory Log

## Index
- [14APR13](#14APR23)
	- [Data](#Data)
- [16APR13](#16APR23)
	- [Using bcftools](#bcftools)
- [19APR13](#19APR23)
	- [DIYABC](#DIYABC)
- [20APR13](#20APR23)
- [21APR13](#21APR23)
- [22APR13](#22APR23)
- [24APR13](#24APR23)
- [25APR13](#25APR23)
- [26APR13](#26APR23)
- [27APR13](#27APR23)
- [28APR13](#28APR23)
- [29APR13](#29APR23)
- [30APR13](#30APR23)
- [01MAY23](#01MAY23)
- [02MAY23](#02MAY23)
- [03MAY23](#03MAY23)
- [04MAY23](#04MAY23)
- [05MAY23](#05MAY23)
- [06MAY23](#06MAY23)
- [07MAY23](#07MAY23)
- [08MAY23](#08MAY23)
- [09MAY23](#09MAY23)
- [10MAY23](#10MAY23)
- [11MAY23](#11MAY23)
- [12MAY23](#12MAY23)
- [13MAY23](#13MAY23)
- [14MAY23](#14MAY23)
- [15MAY23](#15MAY23)
- [16MAY23](#16MAY23)
- [17MAY23](#17MAY23)
- [18MAY23](#18MAY23)
- [19MAY23](#19MAY23)
- [20MAY23](#20MAY23)
- [21MAY23](#21MAY23)
- [22MAY23](#22MAY23)
- [23MAY23](#23MAY23)
- [24MAY23](#24MAY23)
- [25MAY23](#25MAY23)
- [26MAY23](#26MAY23)
- [27MAY23](#27MAY23)
- [28MAY23](#28MAY23)
- [29MAY23](#29MAY23)
- [30MAY23](#30MAY23)
- [31MAY23](#31MAY23)
- [01JUN23](#01JUN23)
- [02JUN23](#01JUN23)
- [03JUN23](#01JUN23)
- [04JUN23](#01JUN23)






## 14APR23 
### Data<a name="Data"></a>







## 16APR23
### Using bcftools<a name="bcftools"></a>
- Installed ubuntu, bcftools

- Duplicated file:  Cakile_e-Admixture_downsampled17721.vcf
-
- Location: sam@DESKTOP-1PAPBN0:/mnt/c/Users/Sam/Documents/Monash/BIO3990$
### Changing sample names
- Edited duplicated names using : 
	- ```bash$ bcftools reheader -s names.txt in.vcf > out.vcf```
	- Output: Cakile_e-Admixture_downsampled17721_rn
	- 'rn' = replaced names
	- Checked in Excel with 'sample_ids' and sample_renames in adjacent columns and command:
	- `=IF(ISNA(MATCH(LEFT(B2,4), LEFT($A$2:$A$399, 4),0)), "No Match", B2)`
	- [![Pasted image 20230417130417.png](https://github.com/samuel-craig/ABC_cakile/blob/main/DIYABC_screengrabs/Pasted%20image%2020230417130417.png "Checking sample_ids in Excel")]
	- Checked by counting samples in bcftools:[![Pasted image 20230417130831.png](https://github.com/samuel-craig/ABC_cakile/blob/main/DIYABC_screengrabs/Pasted%20image%20230417130831.png "Counting samples in bcftools")]
### Check for monomorphic
- To remove monomorphic SNPs, used  `bcftools filter`  to exclude `-e` all sites at which no alternative alleles are called for any of the samples `AC==0` and all sites at which only alternative alleles are called `AC==AN`.
- AC="Allele count in genotypes"
- AN="Total number of alleles in called genotypes"
	- `$ bcftools filter -e 'AC==0 || AC==AN'  Cakile_e-Admixture_downsampled17721_rn >  Cakile_e-Admixture_downsampled17721_rn_poly''
	- Ouput: Cakile_e-Admixture_downsampled17721_rn_poly
	- 'poly' = polymorphic

- Verify the above by counting lines (not including the header)
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721.vcf | wc -l`
Output: 10000
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn | wc -l`
Output: 10000
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly | wc -l`
Output: 10000

? Does this above indicate that monomorphic loci were already filtered out? (this is likely?)
#### ^We will conduct something similar again because the removal of individuals from the VCF file will have led to some sites becoming monomorphic/invariant.
https://evomics.org/wp-content/uploads/2022/06/Population-Genomics-Lab-1.pdf

### Filtering Popfile for C. edentula
- In spreadsheet 'ABC_Edentula_eNA_AUS' filtered so as to keep Australian, Nova Scotian, and Great Lakes Clusters of *C. edentula* subsp. *edentula*
- Great Lakes Cluster appears to be 'K2', includes:
	- Virginia (VA)
	- Maryland (MD),
	- Ontario
	- Michigan
- Spreadsheet ' ABC_Edentula' contains only Australian, Nova Scotian, and Clusters of *C. edentula* subsp. *edentula* so cannot be used to test alternative source population scenarii (such as whether Great Lakes were source, or admixture between Great Lakes and Nova Scotia were source etc)

### Filtering vcf for C. edentula
- Filtered using 'keep_edentula.txt' which is a one-sample-per-line text file taken from spreadsheet 'ABC_Edentula_eNA_AUS' in Popfile
`$ bcftools view -S keep_edentula.txt Cakile_e-Admixture_downsampled17721_rn_poly > Cakile_e-Admixture_downsampled17721_rn_poly_edentula`
Output: Cakile_e-Admixture_downsampled17721_rn_poly_edentula.vcf

- Check number of samples match
``$ bcftools query -l Cakile_e-Admixture_downsampled17721_rn_poly_edentula | wc -l`
Ouput: 90
Output matches number of samples in 'keep_edentula.txt'

#### **Now** filter for monomophic sites with bcftools:
-  `$ bcftools filter -e 'AC==0 || AC==AN'   Cakile_e-Admixture_downsampled17721_rn_poly_edentula >  Cakile_e-Admixture_downsampled17721_edentula_abc'
	- Edentula before:
	`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly_edentula | wc -l`
	10000
	- Edentula after
	`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_edentula_abc | wc -l`
	3877
	- Visualise before and after with:
	- `$bcftools view -H Cakile_e-Admixture_downsampled17721_rn_poly_edentula | less -S`
	- ``$ bcftools view -H Cakile_e-Admixture_downsampled17721_edentula_abc | less -S`
Source: https://evomics.org/learning/population-and-speciation-genomics/2020-population-and-speciation-genomics/first-steps-in-genomic-data-analysis/



### Filtering Popfile for C. maritima
- Filter out 'AUS' from 'Country' column
- Filter out 'H' from 'Sub_Species_Admixture_supervised'
- Remaining samples (101 records):
	- Cluster K1 (Mediterranean): M_eux, M_m
	- Cluster K6 (wNA): M
	- Cluster K7 (Baltic): M_ice, M_eux, M_I
- 'SampleID' column extracted and saved as 'keep_maritima.txt'

### Filtering vcf for C. maritima
- Filtered using 'keep_maritima.txt' which is a one-sample-per-line text file taken from spreadsheet 'ABC_maritima' in Popfile
``$ bcftools view -S keep_maritima.txt Cakile_e-Admixture_downsampled17721_rn_poly > Cakile_e-Admixture_downsampled17721_rn_poly_maritima`
Output:  Cakile_e-Admixture_downsampled17721_rn_poly_maritima.vcf

- Checking number of lines
``$ bcftools query -l Cakile_e-Admixture_downsampled17721_rn_poly_maritima | wc -l`
Output: 101
Output matches number of samples in 'keep_maritima.txt'

#### Filtering for monomorphic sites
- - `$ bcftools filter -e 'AC==0 || AC==AN'   Cakile_e-Admixture_downsampled17721_rn_poly_maritima >  Cakile_e-Admixture_downsampled17721_maritima_abc`
	- Maritima before
	`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly_maritima | wc -l
	10000`
	- Maritima after
	``$ bcftools view -H  Cakile_e Admixture_downsampled17721_maritima_abc | wc -l
	9793
	


### Final output files after name changes and filtering samples and monomorphic:
##### Cakile_e-Admixture_downsampled17721_edentula_abc
##### Cakile_e-Admixture_downsampled17721_maritima_abc


### Finally using vcf2diyabc.py
- Make copies of each final output file label 'cp' at end
- Use bcftools to convert files into vcf using: 
	- `$ bcftools convert --output-type v Cakile_e-Admixture_downsampled17721_edentula_abc_cp > Cakile_e-Admixture_downsampled17721_edentula_abc_cp.vcf `
- Then get the path or `pwd` to where these files are (and where the information files are), make a copy of the path.
- return home with `cd`
- Then `$ cd vcf2DIYABC.snp`
- Then  `$ python2 vcf2diyabc.py`
- You will be prompted to enter your vcf and information files (make sure to include .vcf on the end  of the file). Information files are saved as 'diyabc2vcf_edentula' ...
- DIYABC.snp file will be output on exit.

### Final DIYABC.snp files are called
-  Cakile_e-Admixture_downsampled17721_edentula_abc_cp.DIYABC.snp
- Cakile_e-Admixture_downsampled17721_maritima_abc_cp.DIYABC.snp


## 19APR23

### DIYABC<a name="DIYABC"></a>
#### Question what is the sex ratio?
- DIYABC requires the .snp file header to contain a sex ratio. For C. edentula, I have written this as ``<NM=1NF>``, which - hopefully - means that I expect an equal sex ratio. This has been copied from the majority of the toy datasets within DIYABC, the majority of which seem to specify `<NM=1NF>` and which I interpret as "number of males equals number of females"
- Manual: "or a balanced sex ratio one should write <NM=1.0NF>"
#### Minimum Allele Frequency (MAF)
From the manual: 
- "For instance, the specification of a MAF equal to 5% will automatically select a subset of _m_ loci characterized by a minimum allele frequency ≥ 5% out of the _l_ loci of the observed dataset and only _m_ loci with a MAF ≥ 5% will be retained in a simulated dataset."
- "In practice MAF values ≤10% are considered. To check for the consistency/robustness of the ABC results obtained, it may be useful to treat a SNP dataset considering different MAFs (for instance MAF=hudson, MAF=1% and MAF=5%)."
- # Note the above, treat the dataset with different MAFs


#### Correcting population number
- Make sure that the conversion via vcf2DIYABC doesn't cutoff any popualtion names. For instance in edentula .snp file DIYABC read that there were 4 populations because a 'GL' had been changed to 'G' resulting in 4 populations (AUS, GL, NS and G). This was manually corrected to 'GL'.
- # Note: re-save the edited file as '.snp'
- ##test file saved as edentula_abc_test

#### Correcting scenarii
- if using a time such as `t1-db` the condition setting will read the dash as a minus sign `-`, this will screw up your condition setting. To undo, change any dashes to underscores, i.e. `t1>t1_db`
- Corrected for scenarii 0 & 1 is now:
`tanc>t1
`t1>t1_db
`t1_db<tanc
This means that effective population at time ancestral `tanc>t1` is **always** less than the effective population  at time 1 (divergence, `t1`). `t1_db` is always less than `t1` and `tanc`.



## 20APR23
#### Working out plausible priors
- "In Australia, _C. edentula_ was first recorded in Victoria in 1863 and subsequently spread along the coastline of Australia (Rodman, [1986](https://onlinelibrary.wiley.com/doi/full/10.1111/mec.15768#mec15768-bib-0058))." (Rosinger et al. 2020)
-  The divergence time of the novel population is set to be no later than 1863 and not earlier than 1843. This gives the possibility that _C. edentula_ had arrived two decades earlier, but had not been recorded. (After Byrne et al. 2022 "Bitou")
- These prior settings correspond conservatively to the first observations of  _C. edentula_ in Victoria in 1863 (Rodman 1986).
- _C. edentula_ is annual so generation time equals years. We take the present as 2019:
	- 156 generations/years between 1863-2019
	- 176 generations/years between 1843-2019
- So divergence time of novel AUS _C. edentula_ population is 156-176
-
- "Because of the lack of knowledge of natural and plantation population sizes of _M. ulei_, a uniform distribution with large interval (10–100 000) was chosen as the prior distribution for effective population sizes of the ancestral population (_N_, black in [Figure 2](https://www.nature.com/articles/hdy201237#Fig2)), of the different source populations in the endemism area (_NO_., dark gray in [Figure 2](https://www.nature.com/articles/hdy201237#Fig2)) and of the sampled populations (_N_., light gray in [Figure 2](https://www.nature.com/articles/hdy201237#Fig2))." (Barrès et al. 2012)
- ^ [re-written for edenula] Given the paucity of information regarding the natural population sizes of _C. edentula_, a prior distribution characterized by a uniform distribution with a wide interval (10-10,000) was adopted for effective population sizes pertaining to the ancestral population, the various source populations within the endemism area, and the sampled populations. (Barrès et al. 2012)
- # All priors will be first set to uniform distributions but final models should be simulated under a range of different distributions a la (Barrès et al. 2012) e.g. divergence time should be simulated under a log-uniform distribution.
- "Other distributions (a log-uniform distribution on interval (10–100 000) and a normal distribution with mean 10 000 and standard deviation 20 000) were tested and all results were similar" (Barrès et al. 2012)
- (dummsumm) "Using a log-uniform distribution also has the advantage that it can help avoid the bias that can result from using a uniform distribution, especially when the range of possible values spans several orders of magnitude. In a uniform distribution, the range of possible values is divided into equal intervals on a linear scale, which can result in an overemphasis on the lower end of the range and an underemphasis on the higher end of the range." <- this isn't really a problem for us as our range doesn't span orders of magnitude as (Barrès et al. 2012)'s did (16-500).
- Question the need for '`tadm`' the time of admixture, it may be necessary if we consider admixture occurring a certain amount of time prior to the divergence of the novel population, but not if the admixture event gives rise to the novel population? In which case the admixture rate would simply occur at the time otherwise reserved for the divergence of the Australian population (`t1` in the old model, `taus` in the new)


#### Fixed populations on edentula and maritima files, simulation-ready files are labelled:
- Cakile_e-Admixture_maritima_abc_test.DIYABC.snp
- Cakile_e-Admixture_edentula_abc_test.DIYABC.snp

#### Edentula simulation Pool A: Polytomy and ladderised, single and double bottlenecks
![[Pasted image 20230420135422.png]]
![[Pasted image 20230420140540.png]]
![[Pasted image 20230420140558.png]]
![[Pasted image 20230420140619.png]]
Condition setting
![[Pasted image 20230420140848.png]]
#### Simulate 100,000
- Initial simulation of edentula_pool_A
	- Start: 1410 20APR23
	- End: approx midnight
	- Duration: ~ 10 hours

## 21APR23
#### Simulate more
- Simulate up to 120,000 to ensure >20,000 for each model.
	Start: 0927 21APR23
	End: 1113
	Duration: ~2hrs
#### Initial investigations of edentula Pool A dataset and priors
### Scenario choice
- Save analysis (sub-project) as:
	edentula_pool_A_scenario_choice
- Number of trees
	- DIYABC user manual: "According to our experience, a forest made of 500 to 2,000 trees often constitutes an interesting trade-off between computation efficiency and statistical precision (Breiman, 2001; Chapuis et al. 2020; Pudlo et al. 2016; Raynal et al. 2019). To evaluate whether or not this number is sufficient, we recommend plotting error/accuracy metrics as a function of the number of trees in the forest. The shapes of the curves provide a visual diagnostic of whether such key metrics stabilize when the number of trees tends to a given value. DIYABC-RF provides such a plot-figure as output."
	- 1000 trees chosen
	- modelchoice_out_graph_error_vs_ntrees (edentula Pool A):
	- ![[modelchoice_out_graph_error_versus_ntrees 1.png]]
- Random forest analysis
	- Start: 1119 21APR23
	- End: 1138 21APR23
#### Results
- edentula_pool_A_scenario_choice > modelchoice_out:
model1 | model2 | model3 | model4 | model5 | selected model | post probality 
    577                   6                   1                   314             102                           1                                   0.820
- Model 1 selected
- ![[Pasted image 20230421114847.png]]
#### Interpretation
Interpretation: The expected scenario was scenario 2, which was that the Australian novel population [pop 3] diverged from the Nova Scotian population [pop 1]. This received little support:
![[Pasted image 20230421114952.png]]
- The next highest support was for model 4 (below). This scenario was that the Australian novel population [pop 3] diverged from the Great Lakes population [pop 2]. :
![[Pasted image 20230421115318.png]]


### Parameter Estimation
- Due to ~24,000 simulations for parameter estimation for scenario 1, training set simulation increased to 200,000. This is because 1000-100,000 simulation under the scenario of interest are needed for parameter estimation. Alternatively this could have bee done with a new Project containing solely scenario 1.
- Start: 1205 21APR23
- End:
- Duration:
##### Model 1, tanc
- edentula_pool_A_paramter_est_tanc

### Error
- DIYABC manual: "**samples are considered in the same order as they appear in the data file**"
- So in the previous simulation
	Pop1 = AUS
	Pop2 = NS
	Pop3 =  GL
- As the datasheet cannot(?) be corrected you need to correct the scenarios to reflect the above allocation. This will mean editing the scenarios and losing the simulations conducted up until this point.
- For future reference, the maritima datasheet's sample order is:
	- Pop1  = BL
	- Pop2 = MD
	- Pop3 = WNA

### Correcting scenarios
- New project is loaded over the top of the previous:
	edentula_pool_A

#### All edentula scenarios corrected, priors as per prior spreadsheet
![[Pasted image 20230421194615.png]]
![[Pasted image 20230421194556.png]]
#### Simulation of 200K edentula_Pool_A
- Start: 1947 21APR23
- End: ~2230 22APR23
- Duration: ~39.71 hours

## 22APR23
- Regarding maritima scenarios, what needs to be accounted for is that the divergence event resulting in the population that later is transported to WNA[pop3] may have occurred long prior to it's transport.
- For instance, if an unsampled North African ghost population is was later transported, the scenario prior max/mix for the divergence of this population from another, e.g. pop2[med] could be quite some time in the past. However I think this is already accounted for in the edentula with [tgst] ranging from 177-10,000 years. For maritima, if we want to use two ghost populations to represent two independent dispersal events to WNA, then we just haver to make sure that one dispersal event always occurs before the other via condition seeting, e.g. t1gst>t2gst  
- Regarding edentula, is there any reason we didn't include scenarii where aus diverged directly from a ghost population? Is this because unlike WNA maritima we didn't really see that as a potential based upon the clustering in ADMIXTURE?
- Maritima needs the above scenarii ^, that is a few where a WNA diverges directly from a ghost population (this being one of our key suspicions.)


#### Reading
##### Shaw et al. 2020
- See Sotka et al. 2018 re: the impact of native range on novel populations
- See Rodman 1974 re: edentula var. edentula's appearance in Lake Michigan in historical times (when?) were it is intermixed and perhaps hybridising with var lacustris
- See Riefner 1982, why doesn't maritima persist in edentula's native range in eNA?
- Shaw et al. is trying to answer how many distinct colonisation events there have been and from which source populations.
- See page 606 for how the clades breakdown in eNA
- Re: maritima ". There is a clear geographic separation of clades found only in the eastern Mediterranean (clades C1, C13-C15) and those only in the west-ern Mediterranean (clades C2, C16-C18; Figure 2)."
- up to p.607


## 24APR23
### Scenario Choice
![[Pasted image 20230424084022.png]]
- Edentula pool A
- Saved as subfolder: 'edentula_pool_A_scenario_choice'
- 1000 trees, check graphical output: 'modelchoice_out_graph_error_vs_ntrees'
	- Start: 0723 24APR23
	- End: 0845 24ApR23
	- Duration: ~82min
### Results: Scenario Choice edentula_pool_A
- Predictions File
![[Pasted image 20230424082838.png]]
	- Interpretation: supports the Model 2 with a posterior probability of 0.703
	- Model 2 is the model in which the source population cluster is Nova Scotia.
- Model 2
![[Pasted image 20230424082935.png]]
- Model 2 description: Population 1 [AUS] is derived from population 2[NS] at time [taus]. Population 2 [NS], like population 3 [GL] is the product of a divergence in an ancestral population of size [Nanc] at time [tanc]. At time [tBaus] there has been a demographic bottleneck in population 1 [AUS], resulting in a reduced effective popualtion [NBaus] for a given number of generations.
- Model 3
![[Pasted image 20230424083050.png]]
Model 3 description: same as above but with a double bottleneck.

- Error_vs_ntree
![[modelchoice_out_graph_error_versus_ntrees 1.png]]
- Interpretation: 1000 trees seems sufficient/OOB error becomes constant (and small) even around 500 trees.

### Parameter Estimation
- We have 39822 simulated datasets for scenario 2. The recommended number of simulated datasets is 1,000 to 100,000 so we will proceed with parameter estimation, but may return later with **just** scenario 2 in order to boost this.
- DIYABC manual "In practice, it might be useful to generate a (second) training set including only the selected scenario to process parameter estimation from a larger number of simulated datasets (e.g. 10000 as in Collin et al. 2020)."

#### Ancestral Effective Population
##### File: edentula_pool_A_param_est_Nanc
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Nanc
###### Results
- Expectation: 613.21
![[Pasted image 20230424093715.png]]
###### Interpretation
- 
---

#### Australian Effective Population
##### File: edentula_pool_A_param_est_Naus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Naus
###### Results
- Expectation: 6032.93
![[Pasted image 20230424101119.png]]
###### Interpretation
- 
---


#### Bottlenecked Australian Effective Population
##### File: edentula_pool_A_param_est_NBaus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: NBaus
###### Results
- Expectation 46.67
- Parameter estimation (point estimates)
![[Pasted image 20230424102624.png]]
###### Interpretation
-  
---

#### Great Lakes Effective Population
##### File: edentula_pool_A_param_est_Ngl
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Ngl
###### Results
- Expectation: 899.373
![[Pasted image 20230424105520.png]]
###### Interpretation
- 
---


#### Nova Scotia Effective Population
##### File: edentula_pool_A_param_est_Nns
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Nns
###### Results
- Expectation: 1423.11
![[Pasted image 20230424110758.png]]
###### Interpretation
- 
---

#### Time of Divergence b/n Nova Scotia and Great Lakes
##### File: edentula_pool_A_param_est_tanc
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: tanc
###### Results
- Expectation: 3467.62
![[Pasted image 20230424112804.png]]
###### Interpretation
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Great Lakes populations diverged a median of 2963 years ago, with 95% confidence limits of 721-7837 years ago.
---


#### Time of Divergence b/n Nova Scotia and Australia
##### File: edentula_pool_A_param_est_taus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: taus
###### Results
- Expectation: 165.816
![[Pasted image 20230424114433.png]]
###### Interpretation
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Australian populations diverged a median of 165 years ago, with 95% confidence limits of 157-175 years ago.
---


#### Duration of Bottleneck in Australia
##### File: edentula_pool_A_param_est_tBaus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: tBaus
###### Results
- Expectation: 69.4684
![[Pasted image 20230424120247.png]]
###### Interpretation
- Assuming one generation per year for *C. edentula*, the Australian populations underwent a demographic bottleneck with a median of 75 years ago, with 95% confidence limits of 26-98 years ago.
---

### Parameter Estimation Interpretation
- Stone 2017 "Parameter estimates are presented as median values (with 95% confidence intervals in brackets)"
- Need to compare summary statistics values predicted by the model and those observed by Rosinger et al. 2022.

- # Error
	- # 1. The prior interval for the Australian bottleneck is not wide enough. If you wanted to say that you think that the bottleneck could have gone from the introduction of edentula through to the present, the max value should be 176, as this is the latest point at which the introduction is thought to have occurred.
	- # 2. You did not include any scenarios with which there were *no* bottlenecks present. These are essentially the null models.

### Simulation attempt III
- Project name: ''edentula_A"
- Scenarios 8: added scenario 6, 7, 8 (no bottleneck null models)
- TBaus: Min.  =  1, Max. = 176. This prior was changed to allow for the duration of the bottleneck to have gone on anywhere from the latest/Maximum expected arrival date, 176 generation/years ago, to the present.
- All else the same as previous run
- Same conditions as previous run
- Working with 20,000 simulations per scenario, simulating 160,000 for the 8 scenarios. Will do the same for Pool B and then run parameter estimation separately once a 'winner' between the pools emerges.
	- Start: 1400 24APR23
	- End: CANCELLED
	- Duration: NA
- Simulation cancelled, double bottleneck scenarii 3, 5 removed, scenarii 9, 10, 11 added. Restarted
	- Start: 1615 24APR23
	- End: 1700 25APR23
	- Duration: 24 hours and 45 minutes

##### Consideration: Alternate Prior Sets
- Stone et al. 2017 " Tournament ABC analysis of the western Palaearctic population history of an oak gall wasp, _Synergus umbraculus_"
	- Method:
	1. Pick one model from each pool representing a distinct topology from each class
	2. Feed each model each of the 3 alternate prior sets. These prior sets change only the maximum prior values of *Ne* and *t* 
	e.g. 
	**Prior set  1**
	- N Min.: 10
	- N Max.: 1.5 million
	**Prior set 2**
	- N Min.: 10
	- N Max.: 2.5 million
	3. Take the posterior probability of each model run on each prior set
	4.  Calculate the Bayes Factor
```GPT
give the prior sets 1, 2 and 3 with their respective posterior probabilities 0.930, 0.066, 0.005 calculate the Bayes factor in favor of the most strongly supported prior set.

To calculate the Bayes factor in favor of the most strongly supported prior set, we need to compare the marginal likelihoods of each prior set. We can do this using the posterior probabilities given:

Let Priors 1, 2, and 3 be denoted by P1, P2, and P3, respectively. The marginal likelihoods of the models under each prior set are proportional to the product of the prior probability and the likelihood function:

-   Marginal likelihood under P1 = P(data | model, P1) x P(P1) = K1 x P(P1), where K1 is a constant of proportionality
-   Marginal likelihood under P2 = P(data | model, P2) x P(P2) = K2 x P(P2), where K2 is a constant of proportionality
-   Marginal likelihood under P3 = P(data | model, P3) x P(P3) = K3 x P(P3), where K3 is a constant of proportionality

The constants of proportionality cancel out when we calculate the Bayes factor. Therefore, the Bayes factor in favor of P1 over P2 and P3 is:

-   BF_1/2 = (P1 / P2) = 0.930 / 0.066 = 14.09
-   BF_1/3 = (P1 / P3) = 0.930 / 0.005 = 186.00

Based on these calculations, the most strongly supported prior set is P1, and there is strong evidence in favor of P1 over both P2 and P3. The Bayes factor in favor of P1 over P2 is 14.09, while the Bayes factor in favor of P1 over P3 is 186.00.
```


## 25APR23
- Simulation 'edentula_A' finished. Only files in edentula A created after 24/04/2023 **4:19PM** relate to this simulation.
- Duration: 24 hours and 45 minutes
 ![[Pasted image 20230425170437.png]]
### Random Forest Analysis
- Analysis (sub-project) name:
	- 'edentula_pool_A_scenario_choice'
- 1000 trees
	- Start: 1707 25APR23
	- End:  25APR23
	- Duration:
### Results: Scenario Choice edentula_pool_A
- Predictions File
	![[Pasted image 20230426004029.png]]
	- Interpretation: supports the Model 2 with a posterior probability of 0.63. Model 2 is the model in which the source population cluster is Nova Scotia.
- Model Image
	![[Pasted image 20230426004243.png]]
	- Description: Population 1 [AUS] is derived from population 2[NS] at time [taus]. Population 2 [NS], like population 3 [GL] is the product of a divergence in an ancestral population of size [Nanc] at time [tanc]. At time [tBaus] there has been a demographic bottleneck in population 1 [AUS], resulting in a reduced effective popualtion [NBaus] for a given number of generations.
- Error vs ntree

## 26APR23
### Plan for the next few days
- Complete 'edentula Pool B' simulations
- Compete winner of edentula Pools A and B
	- Write a justification for doing it this way
	- Should you also run a simulation that combines Pools A and B to 'certify' your method?



### Simulation of edentula Pool B
- Project name: 'edentula_B'
- Data file: 'Cakile_e-Admixture_edentula_abc_test.DIYABC.snp'
- Priors as per spreadsheet for pool B priors
- 150,000 simulations (20,000 per model plus 10,000)

- Start: 10:08 26APR23
- End: Sometime around 03:00 27APR23
- Duration: 16 hours and 52 minutes

## 27APR23
- Continuation of edentula pool B project saved as
	- 'edentula_pool_B'
- 10,000 extra simulated datasets added, total will be 160,000 for 7 scenarios.

## 28APR23
### Results of edentula_pool_B simulations
![[Pasted image 20230428133038.png]]
- Model 4 chosen
![[Pasted image 20230428133205.png]]
- Description of model 4: 2 parental populations with constant effective population sizes [Nns] and [Ngl] have diverged at time [tanc] from an ancestral population of size [Nanc]. At time [tgst] Population 2[ns] and Population 4[gst] have diverged. At time [taus], there has been an admixture event between the popualtion 2[ns] and the 'ghost' population 4[gst] giving birth to an admixed population 1[aus] with effective size NBaus at time [tBaus], due to a bottleneck lasting a given number of generations, and with an admixture rate [ra] corresponding to the proportion of genes from Population 2[ns].
- Modelchoice error vs ntrees
- ![[modelchoice_out_graph_error_versus_ntrees 2.png]]

### Tournament between Model 2 Pool A and Model 4 Pool B
- Two scenarios: 
	1. scenario 2 from Pool A
	2. scenario 4 from Pool B
- 50,000 simulations (200,000 per scenario for model choice + 10,000)
	- Start: 1345 28APR23
	- End: 2244 28APR23
	- Duration: 8 hours and 59 minutes.
### Results
![[Pasted image 20230429084106.png]]
Model 1 (Scenario 2 pool A) selected

In *C. edentula* the most strongly supported scenario involved the bottlenecked founding of the Australian cluster by divergence from the Nova Scotian cluster with a posterior probability (PP) of ~0.68. 

## 29APR23
### Parameter estimation, scenario 2 Pool A
- 100,000 simulations under the scenario of interest are needed for parameter estimation.
- I will run this in a new project that just contains one scenario, scenario 2 Pool A.
- Project name: 'edentula_scenario2A_param_est'
- Condition NBaus< Nns added to prior conditions. The bottlenecked effective population cannot be larger than the source population.
- 200,000 simulated datasets, 1 scenario
	- Start: 0852 29APR23
	- End: 0854 30APR23
	- Duration: 25 hours and 2 minutes

## 30APR23 - 01MAY23

### Parameter Estimation
- Number of trees: 1000

### Ancestral Effective Population (Nanc)
##### File: edentula_param_est_Nanc
###### Settings: 
- Number of trees = 1000
- Scenario: 2 (Pool A)
- Parameter: Nanc
- Number of oob testing samples = 1000
	- Start: 1100 30APR23
	- End: 1225 30APR23
	- Duration: 1 hour and 25 minutes

###### Results
- Expectation: 739.613
![[Pasted image 20230430123107.png]]
###### Interpretation
- The effective population of the ancestral *C. edentula* has a median value of 596 and a 90% confidence interval that ranges from 59 to 1858, with the lower and upper bounds corresponding to the 0.05 and 0.95 quantiles, respectively.
---

### Australian Effective Population
##### File: edentula_param_est_Naus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Naus
	- Start: 1235 30APR23
	- End: 1430 30APR23
	- Duration: 1 hour and 55 minutes
###### Results
- Expectation: 6509.83
![[Pasted image 20230430150650.png]]
###### Interpretation
- The effective population of the Australian *C. edentula* has a median value of 6780 and a 90% confidence interval that ranges from 2509 to 9789.
- ## Why is this so high relative to the native populations?
- Rosinger et al. 2022, p. 39:
> "Higher selfing rates in C. edentula would be expected to reduce the effective population size compared to the largely self-in- compatible C. maritima (Pollak, 1987)." 
- Rosinger et al. 2022, p. 43
>"A greater fixation rate of weakly deleterious alleles is predicted in the C. edentula due to its higher level of inbreeding, and indeed, the low levels of genetic variability in this species relative to C.  maritima support a lower effective population size in this species."

---


### Bottlenecked Australian Effective Population
##### File: edentula_param_est_NBaus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: NBaus
	- Start: 1508 30APR23
	- End: 1650 30APR23
	- Duration: 1 hour and 42 minutes
###### Results
- Expectation: 39.2744
![[Pasted image 20230430171423.png]]

###### Interpretation
-  The effective population of the bottlenecked Australian *C. edentula* has a median value of 15 and a 90% confidence interval that ranges from 3 to 69.
---

### Great Lakes Effective Population
##### File: edentula_param_est_Ngl
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Ngl
	- Start: 1715 30APR23
	- End: 1834 30APR23
	- Duration: 1 hour and 19 minutes
###### Results
- Expectation: 997.109
![[Pasted image 20230430190640.png]]
###### Interpretation
- The Great Lakes effective population has a median value of 914 and a 90% confidence interval that ranges from 298 to 1903.
---


### Nova Scotia Effective Population
##### File: edentula_param_est_Nns
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: Nns
	- Start: ~1900 30APR23
	- End: 2017 30APR23
	- Duration: 1hrs 17min
###### Results
- Expectation: 
- 1562.72
![[Pasted image 20230501080053.png]]
###### Interpretation
- The Nova Scotian effective population has a median value of 1,273 and a 90% confidence interval that ranges from 500 to 3562. 
---
01MAY23
### Time of Divergence b/n Nova Scotia and Great Lakes
##### File: edentula_param_est_tanc
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: tanc
	- Start: 0802 01MAY23
	- End: 0927 01MAY23
	- Duration: 1 hour and 25min
###### Results
- Expectation: 4979.95
![[Pasted image 20230501094213.png]]
###### Interpretation
- The Nova Scotian and Great Lakes populations of _C. edentula_ diverged approximately 2,963 years ago (assuming one generation per year). The 90% confidence interval for this estimate ranges from 721 to 7,837 years ago.
---


### Time of Divergence b/n Nova Scotia and Australia
##### File: edentula_pool_A_param_est_taus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: taus
	- Start: 0943 01MAY23
	- End: 1207 01MAY23
	- Duration: 2 hours and 24 minutes
###### Results
- Expectation: 165.746
![[Pasted image 20230501121344.png]]
###### Interpretation
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Australian populations diverged a median of 166 years ago, with a 95% confidence interval of 157-175 years ago.
---


### Duration of Bottleneck in Australia
##### File: edentula_param_est_tBaus
###### Settings: 
- Number of trees = 1000
- Scenario: 2
- Parameter: tBaus
###### Results
- Expectation: 108.152
![[Pasted image 20230501143642.png]]
###### Interpretation
- Assuming one generation per year for *C. edentula*, the novel Australian population was bottlenecked for 111 years, with 95% confidence interval of 46-157 years ago.
---

### Parameter Estimation Interpretation
- Stone 2017 "Parameter estimates are presented as median values (with 95% confidence intervals in brackets)"
- Need to compare summary statistics values predicted by the model and those observed by Rosinger et al. 2022.

## 05MAY23
### Maritima scenarios
- Rosinger et al. 2022: "Cakile maritima reached western North America in 1935 at Stinson Bay (close to San Francisco), and was first observed sympatric with C. edentula (Barbour & Rodman, 1970)"
- 2019-1935 = 84, [84-104]

### Maritima scenarios
- Saved as: maritima_pool_A
- Using file: Cakile_e-Admixture_maritima_abc_test.DIYABC
- 9 scenarios: see 'Scenarii_maritima' tab in 'Scenarii' workbook for details
![[Pasted image 20230508130359.png]]
- Conditions:
	- tanc>tgst
	- tanc>twna
	- tanc>tBwna
	- tgst>twna
	- tgst>tBwna
	- twna>tBwna
	- Nmd>NBwna
	- Nbl>NBwna
	- Ngst>NBwna

9 scenarios, 200,000 simulated datasets
	- Start: 1336 05MAY23
	- End: 2005 08MAY23
	- Duration: 2 days, 6 hours, and 29 minutes.

## 06MAY23

## 07MAY23

## 08MAY23
![[Pasted image 20230511200816.png]]
model choice: maritima_pool_A_scenario_choice
1000 trees
start 2007 11MAY23
end 0938
duration:
Result:
![[Pasted image 20230511213853.png]]
## 09MAY23
- Should two sets of maritima admixture scenarios be separated into pool B and Pool C? Pool B with pre-introduction admixture and Pool C with post-introduction admixture?
- # Error. You need to run edentula pool B scenarios again.
	- # Why?
	- For the edentula scenarios you constrained the window of time in which admixture to occur to between 156 and 176 years.
	- This means that the admixture event either happened only immediately prior to transportation to Australia or immediately prior (within a 20 year window)
	- You already had the solution to this, pre-introduction admixture was meant to be set to the parameter [tadm] with a U[177-10,000]. This would have allowed admixture to have occurred in the native range up until the divergence event that split away part of a population to Australia.
- # Note:
- For the edentula admixture scenarios you are only really saying that the admixture occurs between 156 and 176 years ago - that is that the admixture only occurred within the window of time the plant was recorded in Australia (so these are post-introduction admixture events that you are testing, not admixture prior to arrival in Australia) <- is that what you wanted to test? Because our prior belief was that there was only a single introduction of edentula and this tests that there were multiple introductions form different populations that then admixed <- also it doesn't really test that there were multiple introductions from the same source population at different points in time (are these capture by Pool A's single introduction scenarios?)
- Note on the above. Yes the scenarios for edentula are that there were separate populations in Nova Scotia, Great Lakes and Ghost and that within the 20 year window of the discovery of edentula in Australia, these separate populations may have been combined/admixed in Australia, resulting in a new, admixed population to be created in Australia. The admixture event occurs within the same 'window of time' as the divergence event. What *Should* have been included here is that population bottlenecks should have been introduced for the entirety of this window of time: ie. diverge from source (156-176 years ago) -> bottleneck (0-20 years long) -> admixture (156-176 years ago) -> bottleneck (0-176 years long)
- # 
## 10MAY23
- Lab meeting 1200
- 3990 meeting 1400

## 11MAY23 




## 12MAY23
Maritima pool C scenario writing



-Condition Setting
```
tanc>twna # the ancestral div is before the first intro
tanc>tBwna # the ancestral div is before the first intro DB
tanc>twna2 # the ancestral div is before the second intro
tanc>tBwna2 # the ancestral div is before the second DB 
tanc>tpost # the ancestral div is before the admixture event
twna>tBwna # The first intro is before the DB 
twna>twna2 # the first intro is before the second intro
twna>tBwna2 # the first intro is before the second intro DB
twna>tpost # the first intro is before the admixture event
twna2>tBwna2 # The secondary intro is before the bottleneck
twna2>tpost # the secondary intro is before an admixture event
NBgst1<Ngst1 # The DB population is less than the non-DB population
NBgst2<Ngst2 # DB population is less than the non-DB population
```

Start: 1519 12MAY23
End:  paused 1617 12MAY23 - need to prioritise simulation of C. edentula Pool C

Simulation
200,000 to get at least 20,000 per scenario
edentula_pool_C
start:1623 12MAY
end: 10:55 13MAY
duration:

Poster introduction, aims, methods, results, conclusion written.


## 13MAY23
0300 Poster work

Random forest saved as:
edentula_pool_C_model_choice
1000 trees
start: 1428 13MAY23
end: 1537 13MAY23
Result
![[Pasted image 20230513153834.png]]
Selected model 6 with PP 0.606
![[Pasted image 20230513154019.png]]
At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[ns],  pop3[gl] and pop6[gst3] split. At time [taus] pop4 [gst1] splits off pop6[gst3] and is bottlenecked for time [tBaus] resulting in Ne of [NBgst1]. Later (more recently) at time [tBaus2] pop 5[gst2] splits off pop6[gst3] and is bottlenecked for time [tBaus2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop1 [aus] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra]. 
#### Interpretation: very interesting, would have thought that it would have picked something more closely related to Nova Scotia


### Tournament between Model 2 Pool A,  Model 4 Pool B, and Model 6 Pool C 
- Three scenarios: 
	1. scenario 2 from Pool A
	2. scenario 4 from Pool B
	3. scenario 6 from Pool C
- File name: "edentula_A_B_C"
 ``` Conditons
tanc>taus
tanc>tgst
tanc>tBaus
tanc>taus2
tanc>tBaus2
tanc>tpost
tgst>taus
taus>tBaus
taus>taus2
taus>tBaus2
taus>tpost
taus2>tBaus2
taus2>tpost
NBgst1<Ngst1
NBgst2<Ngst2
Nns>NBaus
Nns>Ngst
```

- 50,000 simulations (20,000 per scenario for model choice + 10,000)
	- Start: 1619 13MAY23  [ CRASH ] reset 1658 13MAY23
	- End: 2302 13MAY23
	- Duration:

run 1000 trees
- Start 2306 13MAY23
- End:23:56 13MAY23
- Duration
- Results
- ![[Pasted image 20230513235709.png]]

- 2230: Completed phylogeny photograph diagram for Poster


## 14MAY23
Poster: diagram in Adobe Illustrator, composite image Photoshop

## 15MAY23
Poster completion, submission 1837 15MAY23

## 16MAY23
### Maritima Pool C simulation
- Resume: maritima pool C simulation
- Load from existing project 'maritima_pool_c'
	- headerRF.txtx
	- statobsRF.txt
	- reftableRF.bin
![[Pasted image 20230516080750.png]]
Simulations: 200,000
Start 0808 16MAY23
End: 1502 18MAY23
Duration: 30 hours, 55 minutes


### Random Forest Analysis: Model Choice Pool C
Number of trees: 1000
Start: 1635 18MAY23
End: 1711 18MAY23
Duration: 36 minutes

### Model Choice Pool C Result
![[Pasted image 20230523085014.png]]
Model 4 chosen, very slim margin between models 4, 9, 5 and 6

### Model Image
![[Pasted image 20230524143913.png]]
### Model Description
At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[med],  pop1[balt] and pop6[gst3] split. At time [twna] pop4 [gst1] splits off pop6[gst3] and is bottlenecked for time [tBwna] resulting in Ne of [NBgst1]. Later (more recently) at time [tBwna2] pop 5[gst2] splits off pop1[balt] and is bottlenecked for time [tBwna2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop3 [wna] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra].

## 20MAY23
### Dataset Simulation: Maritima pool B
- Conditons:
tanc>tgst
tanc>tadm
tanc>twna
tanc>tBwna
tgst>tadm
tgst>twna
tgst>tBwna
tadm>twna
tadm>tBwna
twna>tBwna
Ngst>NBwna

Changed Pool C reflect the possibility of pre-invasion admixture, allowing admixture to occur prior to likely invasion time [105-10,000].


Start: 2132 20MAY23
End: 1939 22MAY 23
Duration: 46 hours, 7 minutes

## 22MAY23
![[Pasted image 20230522194550.png]]
- maritima_pool_B_scenario_choice
- 5 noise variables
- 1000 trees
- Start: 1946 22MAY23
- End: 2041 22MAY 23
- Duration: 55 minutes

Results:
![[Pasted image 20230523084808.png]]
Model 1 selected by only 1 vote.

## 23MAY23
Tournament between winners (and scenarios within 10 votes of the winning scenario - too close to differentiate) of poll A, B, C
- File name: 'maritima_A_B_C'
1. Scenario 2 Pool A;
2. Scenario 1 Pool B;
3. Scenario 2 Pool B;
4. Scenario 4 Pool C;
5. Scenario 5 Pool C
6. Scenario 6 Pool C
7. Scenario 9 Pool C
![[Pasted image 20230523090507.png]]
- Same priors as per each Pool's individual priors
- Conditions in spreadsheet, tab 'Priors_maritima'
- 150,000 datasets (at least 20,000 per scenario)
- Start: 0932 23MAY23
- End:
- Duration:
