# Laboratory Log

## Index
- [14APR13](#14APR23)
	- [Data](#Data)
- [16APR13](#16APR23)
	- [Using bcftools](#bcftools)
- [19APR13](#19APR23)
	- [DIYABC](#DIYABC)
- [20APR13](#20APR23)
	- [*C. edentula* Priors](#edentula_priors)
	- [Dataset Simulation: *C. edentula* Pool A](#edentula_sim_A1)
- [21APR13](#21APR23)
	- [Scenario Choice: *C. edentula* Pool A](#edentula_sc_a)
	- [Error: Order of Populations](#error1)
- [22APR13](#22APR23)
- [24APR13](#24APR23)
	- [Scenario Choice: *C. edentula* Pool A](#edentula_sc_24)
	- [Parameter Estimation: *C. edentula* Pool A](#edentula_pe_24)
	- [Error: Prior Intervals](#error2)
	- [Dataset Simulation: *C. edentula* Pool A, v.3](#edentula_sim_24) 
- [25APR13](#25APR23)
	- [Scenario Choice: *C. edentula* Pool A](#edentula_sc_25)
- [26APR13](#26APR23)
	- [Dataset Simulation: *C. edentula* Pool B](#edentula_sim_26)
- [27APR13](#27APR23)
	- [Scenario Choice: *C. edentula* Pool B](#edentula_sc_27)
- [28APR13](#28APR23)
	- [Scenario Tournament: *C. edentula*](#edentula_tourn_28)
- [29APR13](#29APR23)
	- [Parameter Estimation: *C. edentula*](#edentula_pe_29)
- [30APR13](#30APR23)
- [01MAY23](#01MAY23)
	- [Parameter Estimation: *C. edentula*](#edentula_pe_30)
- [02MAY23](#02MAY23)
- [03MAY23](#03MAY23)
- [04MAY23](#04MAY23)
- [05MAY23](#05MAY23)
	- [Dataset Simulation: *C. maritima* Pool A](#maritima_sim_05)
- [06MAY23](#06MAY23)
- [07MAY23](#07MAY23)
- [08MAY23](#08MAY23)
	- [Scenario Choice: *C. maritima* Pool A](#maritima_sc_08)
- [09MAY23](#09MAY23)
	- [Developing Scenario Pool C](#scenario_pool_c)
- [10MAY23](#10MAY23)
- [11MAY23](#11MAY23)
- [12MAY23](#12MAY23)
	- [Dataset Simulation: *C. maritima* Pool C](#maritima_sim_12)
- [13MAY23](#13MAY23)
	- [Dataset Simulation: *C. edentula* Pool C](#edentula_sc_13)
	- [Scenario Tournament: *C. edentula*](#edentula_tourn_13)
- [14MAY23](#14MAY23)
- [15MAY23](#15MAY23)
- [16MAY23](#16MAY23)
	- [Dataset Simulation: *C. maritima* Pool C](#maritima_sim_16)
	- [Scenario Choice: *C. Maritima* Pool C](#maritima_sc_16)
- [17MAY23](#17MAY23)
- [18MAY23](#18MAY23)
- [19MAY23](#19MAY23)
- [20MAY23](#20MAY23)
	- [Dataset Simulation: *C. maritima* Pool B](#maritima_sim_20)
- [21MAY23](#21MAY23)
- [22MAY23](#22MAY23)
	- [Scenario Choice: *C. maritima* Pool B](#maritima_sc_22)
- [23MAY23](#23MAY23)
	- [Scenario Tournament: *C. maritima*](#maritima_tourn_23)
- [24MAY23](#24MAY23)
- [25MAY23](#25MAY23)
	- [Scenario Choice: *C. maritima*](#maritima_sc_25)
	- [Parameter Estimation: *C. maritima*](#maritima_pe_25)
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

- [09JUL23](#09JUL23)
	- [Updating log: Jun-Jul](#Updating_log_Jun_Jul)
- [10JUL23](#10JUL23)
- [11JUL23](#11JUL23)
- [12JUL23](#12JUL23)
- [13JUL23](#13JUL23)
- [14JUL23](#14JUL23)
- [15JUL23](#15JUL23)
- [16JUL23](#16JUL23)
- [17JUL23](#17JUL23)
	- [Results from JUL simulations](#JUL_simulations)
- [18JUL23](#18JUL23)
- [19JUL23](#19JUL23)
- [20JUL23](#20JUL23)
- [21JUL23](#21JUL23)
- [22JUL23](#22JUL23)
- [23JUL23](#23JUL23)
- [24JUL23](#24JUL23)
- [25JUL23](#25JUL23)
- [26JUL23](#26JUL23)
- [27JUL23](#27JUL23)
- [28JUL23](#28JUL23)
- [29JUL23](#29JUL23)
- [30JUL23](#30JUL23)
- [31JUL23](#31JUL23)








## 14APR23
### Data<a name="Data"></a>
- Received vcf files, converted from plink by Kay, and Popfile spreadsheet from Hanna. 

## 16APR23
### Using bcftools<a name="bcftools"></a>
- Installed ubuntu, bcftools
- Duplicate file: Cakile_e-Admixture_downsampled17721.vcf

- Location: sam@DESKTOP-1PAPBN0:/mnt/c/Users/Sam/Documents/Monash/BIO3990$
### Changing sample names
- Edited duplicated names using : 
	- ```bash$ bcftools reheader -s names.txt in.vcf > out.vcf```
	- Output: Cakile_e-Admixture_downsampled17721_rn
	- 'rn' = replaced names
	- Checked in Excel with 'sample_ids' and sample_renames in adjacent columns and command:
	- `=IF(ISNA(MATCH(LEFT(B2,4), LEFT($A$2:$A$399, 4),0)), "No Match", B2)`
	- ![Pasted image 20230417130417.png](https://github.com/samuel-craig/ABC_cakile/blob/main/DIYABC_screengrabs/Pasted%20image%2020230417130417.png "Checking sample_ids in Excel")
	- Checked by counting samples in bcftools:![Pasted image 20230417130831.png](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230417130831.png)
### Check for monomorphic
- To remove monomorphic SNPs, used  `bcftools filter`  to exclude `-e` all sites at which no alternative alleles are called for any of the samples `AC==0` and all sites at which only alternative alleles are called `AC==AN`.
- `AC`="Allele count in genotypes"
- `AN`="Total number of alleles in called genotypes"
	- `$ bcftools filter -e 'AC==0 || AC==AN'  Cakile_e-Admixture_downsampled17721_rn >  Cakile_e-Admixture_downsampled17721_rn_poly`
	- Ouput: Cakile_e-Admixture_downsampled17721_rn_poly
	- `poly` = polymorphic

### Verify the above by counting lines (not including the header)
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721.vcf | wc -l`
Output: 10000
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn | wc -l`
Output: 10000
`$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly | wc -l`
Output: 10000

#### ? Does this above indicate that monomorphic loci were already filtered out? (this is likely?)
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
`$ bcftools query -l Cakile_e-Admixture_downsampled17721_rn_poly_edentula | wc -l`
Ouput: 90
Output matches number of samples in 'keep_edentula.txt'

#### **Now** filter for monomophic sites with bcftools:
`$ bcftools filter -e 'AC==0 || AC==AN'   Cakile_e-Admixture_downsampled17721_rn_poly_edentula >  Cakile_e-Admixture_downsampled17721_edentula_abc'
- Edentula before:
`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly_edentula | wc -l`
10000
- Edentula after
`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_edentula_abc | wc -l`
3877
- Visualise before and after with:
- `$bcftools view -H Cakile_e-Admixture_downsampled17721_rn_poly_edentula | less -S`
- `$ bcftools view -H Cakile_e-Admixture_downsampled17721_edentula_abc | less -S`

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
`$ bcftools view -S keep_maritima.txt Cakile_e-Admixture_downsampled17721_rn_poly > Cakile_e-Admixture_downsampled17721_rn_poly_maritima`
Output:  Cakile_e-Admixture_downsampled17721_rn_poly_maritima.vcf

- Checking number of lines
`$ bcftools query -l Cakile_e-Admixture_downsampled17721_rn_poly_maritima | wc -l`
Output: 101
Output matches number of samples in 'keep_maritima.txt'

#### Filtering for monomorphic sites
`$ bcftools filter -e 'AC==0 || AC==AN'   Cakile_e-Admixture_downsampled17721_rn_poly_maritima >  Cakile_e-Admixture_downsampled17721_maritima_abc`
- Maritima before
`/mnt/c/Users/Sam/Documents/Monash/BIO3990$ bcftools view -H  Cakile_e-Admixture_downsampled17721_rn_poly_maritima | wc -l`
- 10000
- Maritima after
`$ bcftools view -H  Cakile_e Admixture_downsampled17721_maritima_abc | wc -l`
 9793
	


### Final output files after name changes and filtering samples and monomorphic:
##### Cakile_e-Admixture_downsampled17721_edentula_abc
##### Cakile_e-Admixture_downsampled17721_maritima_abc


### Finally using vcf2diyabc.py
- Make copies of each final output file label 'cp' at end
- Use bcftools to convert files into vcf using: 
`$ bcftools convert --output-type v Cakile_e-Admixture_downsampled17721_edentula_abc_cp > Cakile_e-Admixture_downsampled17721_edentula_abc_cp.vcf `
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
`tanc>t1`
`t1>t1_db`
`t1_db<tanc`
This means that effective population at time ancestral `tanc>t1` is **always** less than the effective population  at time 1 (divergence, `t1`). `t1_db` is always less than `t1` and `tanc`.



## 20APR23
### _C. edentula_ Priors<a name="edentula_priors"></a>
#### Working out plausible priors
- "In Australia, _C. edentula_ was first recorded in Victoria in 1863 and subsequently spread along the coastline of Australia (Rodman, [1986](https://onlinelibrary.wiley.com/doi/full/10.1111/mec.15768#mec15768-bib-0058))." (Rosinger et al. 2020)
-  The divergence time of the novel population is set to be no later than 1863 and not earlier than 1843. This gives the possibility that *C. edentula* had arrived two decades earlier (mentioned by Cousens that locals on Phillip Island had seen C. edentula around for two decades prior to the first collection being made) - but had not been recorded. (After Byrne et al. 2022 “Bitou”)
- These prior settings correspond conservatively to the first observations of  _C. edentula_ in Victoria in 1863 (Rodman 1986).
- _C. edentula_ is annual so generation time equals years. We take the present as 2019:
	- 156 generations/years between 1863-2019
	- 176 generations/years between 1843-2019
- So divergence time of novel AUS _C. edentula_ population is 156-176

- Mthods -> Given the paucity of information regarding the natural population sizes of _C. edentula_, a prior distribution characterized by a uniform distribution with a wide interval (10-10,000) was adopted for effective population sizes pertaining to the ancestral population, the various source populations within the endemism area, and the sampled populations. (Barrès et al. 2012)
- All priors will be first set to uniform distributions but final models should be simulated under a range of different distributions a la (Barrès et al. 2012) e.g. divergence time should be simulated under a log-uniform distribution.
- "Other distributions (a log-uniform distribution on interval (10–100 000) and a normal distribution with mean 10 000 and standard deviation 20 000) were tested and all results were similar" (Barrès et al. 2012)
- (Barrès et al. 2012): Using a log-uniform distribution also has the advantage that it can help avoid the bias that can result from using a uniform distribution, especially when the range of possible values spans several orders of magnitude. In a uniform distribution, the range of possible values is divided into equal intervals on a linear scale, which can result in an overemphasis on the lower end of the range and an underemphasis on the higher end of the range. <- this isn't really a problem for us as our range doesn't span orders of magnitude as (Barrès et al. 2012)'s did (16-500).
- Question the need for '`tadm`' the time of admixture, it may be necessary if we consider admixture occurring a certain amount of time prior to the divergence of the novel population, but not if the admixture event gives rise to the novel population? In which case the admixture rate would simply occur at the time otherwise reserved for the divergence of the Australian population (`t1` in the old model, `taus` in the new)


#### Fixed populations on edentula and maritima files, simulation-ready files are labelled:
- Cakile_e-Admixture_maritima_abc_test.DIYABC.snp
- Cakile_e-Admixture_edentula_abc_test.DIYABC.snp

#### Edentula simulation Pool A: Polytomy and ladderised, single and double bottlenecks<a name="edentula_sim_A1"></a>
![[Pasted image 20230420135422.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230420135422.png "edentula pool A scenarii")
![[Pasted image 20230420140540.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230420140540.png "Priors")
![[Pasted image 20230420140558.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230420140558.png)
![[Pasted image 20230420140619.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230420140619.png)

###### CONDTIONS:

![[Pasted image 20230420140848.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230420140848.png "Conditions")

#### Dataset Simulation
- Initial simulation of edentula_pool_A
###### SIMULATION SETTINGS:
- 100,000 datasets
	- Start: 1410 20APR23
	- End: approx midnight
	- Duration: ~ 10 hours

## 21APR23
#### Dataset Simulation cont.
###### SIMULATION SETTINGS:
- Simulate up to 120,000 to ensure >20,000 for each model.
	- Start: 0927 21APR23
	- End: 1113
	- Duration: ~2hrs
#### Initial investigations of edentula Pool A dataset and priors
### Scenario choice: *C. edentula* Pool A<a name="edentula_sc_a"></a> 
- Save analysis (sub-project) as:
	edentula_pool_A_scenario_choice
- Number of trees
	- DIYABC user manual: "According to our experience, a forest made of 500 to 2,000 trees often constitutes an interesting trade-off between computation efficiency and statistical precision (Breiman, 2001; Chapuis et al. 2020; Pudlo et al. 2016; Raynal et al. 2019). To evaluate whether or not this number is sufficient, we recommend plotting error/accuracy metrics as a function of the number of trees in the forest. The shapes of the curves provide a visual diagnostic of whether such key metrics stabilize when the number of trees tends to a given value. DIYABC-RF provides such a plot-figure as output."
	- 1000 trees chosen
	- modelchoice_out_graph_error_vs_ntrees (edentula Pool A):
![[modelchoice_out_graph_error_versus_ntrees 1.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/edentula_pool_A_v1.JPG "modelchoice_out_graph_error_vs_ntrees")

###### RF ANALYSIS SETTINGS:
- 1000 trees
	- Start: 1119 21APR23
	- End: 1138 21APR23
###### RESULTS:
- edentula_pool_A_scenario_choice > modelchoice_out:

|model1 | model2 | model3 | model4 | model5 | selected model | post probality |
|-------|--------|--------|--------|--------|----------------|----------------|
|  577  |    6   |   1    |   314  | 102    |      1         |      0.820     |

- Model 1 selected

![[Pasted image 20230421114847.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230421114847.png "Model 1, Pool A")

#### INTERPRETATION:
Interpretation: The expected scenario was scenario 2, which was that the Australian novel population [pop 3] diverged from the Nova Scotian population [pop 1]. This received little support:

![[Pasted image 20230421114952.png]]

- The next highest support was for model 4 (below). This scenario was that the Australian novel population [pop 3] diverged from the Great Lakes population [pop 2].:

![[Pasted image 20230421115318.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230421114952.png "Model 4, Pool A")


### Parameter Estimation
- Due to ~24,000 simulations for parameter estimation for scenario 1, training set simulation increased to 200,000. This is because 1000-100,000 simulation under the scenario of interest are needed for parameter estimation. Alternatively this could have bee done with a new Project containing solely scenario 1.
	- Start: 1205 21APR23
	- End:
	- Duration:
##### Model 1, tanc
- edentula_pool_A_paramter_est_tanc

### ERROR<a name="error1"></a>
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

![[Pasted image 20230421194615.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230421194615.png)

![[Pasted image v.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230421194556.png)

###### SIMULATION SETTINGS:
- Simulation of 200K edentula_Pool_A
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
### Scenario Choice: *C. edentula* Pool A<a name="edentula_sc_24"></a>

![[Pasted image 20230424084022.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424084022.png "Number of simulated datasets and parameters")


###### FILE: edentula_pool_A_scenario_choice
###### RF ANALYSIS SETTINGS:
- 1000 trees, check graphical output: 'modelchoice_out_graph_error_vs_ntrees'
	- Start: 0723 24APR23
	- End: 0845 24ApR23
	- Duration: ~82min
###### RESULTS:
- Scenario Choice edentula_pool_A
- Predictions File

![[Pasted image 20230424082838.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424082838.png)

###### INTERPRETATION:
- supports the Model 2 with a posterior probability of 0.703
- Model 2 is the model in which the source population cluster is Nova Scotia.

- Model 2

![[Pasted image 20230424082935.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424082935.png "edentula pool A model 2")

###### MODEL DESCRIPTION: Population 1 [AUS] is derived from population 2[NS] at time [taus]. Population 2 [NS], like population 3 [GL] is the product of a divergence in an ancestral population of size [Nanc] at time [tanc]. At time [tBaus] there has been a demographic bottleneck in population 1 [AUS], resulting in a reduced effective popualtion [NBaus] for a given number of generations.
- Model 3

![[Pasted image 20230424083050.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424083050.png "edentula pool A model 3")

###### MODEL DESCRIPTION:  
- same as above but with a double bottleneck.

#### Error_vs_ntree

![[modelchoice_out_graph_error_versus_ntrees 1.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/edentula_pool_A_v2.JPG)

###### INTERPRETATION: 
- 1000 trees seems sufficient/OOB error becomes constant (and small) even around 500 trees.

### Parameter Estimation<a name="edentula_pe_24"></a>
- We have 39822 simulated datasets for scenario 2. The recommended number of simulated datasets is 1,000 to 100,000 so we will proceed with parameter estimation, but may return later with **just** scenario 2 in order to boost this.
- DIYABC manual "In practice, it might be useful to generate a (second) training set including only the selected scenario to process parameter estimation from a larger number of simulated datasets (e.g. 10000 as in Collin et al. 2020)."

#### Ancestral Effective Population
###### FILE: edentula_pool_A_param_est_Nanc
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Nanc
###### RESULTS:
- Expectation: 613.21

![[Pasted image 20230424093715.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424093715.png)

###### Interpretation
- 
---

#### Australian Effective Population
###### FILE: edentula_pool_A_param_est_Naus
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Naus
###### RESULTS:
- Expectation: 6032.93

![[Pasted image 20230424101119.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424101119.png)

###### Interpretation
- 
---


#### Bottlenecked Australian Effective Population
###### FILE: edentula_pool_A_param_est_NBaus
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: NBaus
###### RESULTS:
- Expectation 46.67
- Parameter estimation (point estimates)

![[Pasted image 20230424102624.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424102624.png)

###### Interpretation
-  
---

#### Great Lakes Effective Population
###### FILE: edentula_pool_A_param_est_Ngl
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Ngl
###### RESULTS:
- Expectation: 899.373

![[Pasted image 20230424105520.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424105520.png)

###### Interpretation
- 
---


#### Nova Scotia Effective Population
###### FILE: edentula_pool_A_param_est_Nns
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Nns
###### RESULTS:
- Expectation: 1423.11

![[Pasted image 20230424110758.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424110758.png)

###### Interpretation
- 
---

#### Time of Divergence b/n Nova Scotia and Great Lakes
###### FILE: edentula_pool_A_param_est_tanc
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: tanc
###### RESULTS:
- Expectation: 3467.62

![[Pasted image 20230424112804.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424112804.png)

###### Interpretation
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Great Lakes populations diverged a median of 2963 years ago, with 95% confidence limits of 721-7837 years ago.
---


#### Time of Divergence b/n Nova Scotia and Australia
###### FILE: edentula_pool_A_param_est_taus
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: taus
###### RESULTS:
- Expectation: 165.816

![[Pasted image 20230424114433.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424114433.png)

###### Interpretation
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Australian populations diverged a median of 165 years ago, with 95% confidence limits of 157-175 years ago.
---


#### Duration of Bottleneck in Australia
###### FILE: edentula_pool_A_param_est_tBaus
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: tBaus
###### RESULTS:
- Expectation: 69.4684

![[Pasted image 20230424120247.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230424120247.png)

###### INTERPRETATION
- Assuming one generation per year for *C. edentula*, the Australian populations underwent a demographic bottleneck with a median of 75 years ago, with 95% confidence limits of 26-98 years ago.
---

### Parameter Estimation Interpretation
- Stone 2017 "Parameter estimates are presented as median values (with 95% confidence intervals in brackets)"
- Need to compare summary statistics values predicted by the model and those observed by Rosinger et al. 2022.

- # ERROR<a name="error2"></a>
	- # 1. The prior interval for the Australian bottleneck is not wide enough. If you wanted to say that you think that the bottleneck could have gone from the introduction of edentula through to the present, the max value should be 176, as this is the latest point at which the introduction is thought to have occurred.
	- # 2. You did not include any scenarios with which there were *no* bottlenecks present. These are essentially the null models.

### Simulation attempt v.3<a name="edentula_sim_24"></a>
###### FILE: ''edentula_A"
###### SIMULATION SETTINGS:
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
```Bayes Factor Calculation Example
E.g. Give the prior sets 1, 2 and 3 with their respective posterior probabilities 0.930, 0.066, 0.005 calculate the Bayes factor in favor of the most strongly supported prior set.

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

 ![[Pasted image 20230425170437.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230425170437.png)

### Scenario Choice: *C. edentula* Pool A (v.3)<a name="edentula_sc_25"></a>
###### FILE: edentula_pool_A_scenario_choice
###### RF ANALYSIS SETTINGS:
- 1000 trees
	- Start: 1707 25APR23
	- End:  25APR23
	- Duration:
###### RESULTS:
Scenario Choice edentula_pool_A
- Predictions File

![[Pasted image 20230426004029.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230426004029.png)

###### INTERPRETATION:
Supports the Model 2 with a posterior probability of 0.63. Model 2 is the model in which the source population cluster is Nova Scotia.

###### MODEL IMAGE:

![[Pasted image 20230426004243.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230426004243.png "edentula Pool A model 2")

###### MODEL DESCRIPTION:
Population 1 [AUS] is derived from population 2[NS] at time [taus]. Population 2 [NS], like population 3 [GL] is the product of a divergence in an ancestral population of size [Nanc] at time [tanc]. At time [tBaus] there has been a demographic bottleneck in population 1 [AUS], resulting in a reduced effective popualtion [NBaus] for a given number of generations.


## 26APR23
### Plan for the next few days
- Complete 'edentula Pool B' simulations
- Compete winner of edentula Pools A and B
	- Write a rationale for using Byrne’s tournament method.
	- Should you also run a simulation that combines Pools A and B to 'certify' your method?



### Dataset Simulation: *C. edentula* Pool B<a name="edentula_sim_26"></a>
###### FILE: edentula_B
- Data file: 'Cakile_e-Admixture_edentula_abc_test.DIYABC.snp'
- Priors as per spreadsheet for pool B priors

###### SIMULATION SETTINGS:
- 150,000 simulations (20,000 per model plus 10,000)
	- Start: 10:08 26APR23
	- End: Sometime around 03:00 27APR23
	- Duration: 16 hours and 52 minutes

## 27APR23
- Continuation of edentula pool B project saved as
	- 'edentula_pool_B'
- 10,000 extra simulated datasets added, total will be 160,000 for 7 scenarios.

## 28APR23
### Scenario Choice: *C. edentula* Pool B<a name="edentula_sc_27"></a>

![[Pasted image 20230428133038.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230428133038.png)

- Model 4 chosen

![[Pasted image 20230428133205.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230428133205.png)

- Description of model 4: 2 parental populations with constant effective population sizes [Nns] and [Ngl] have diverged at time [tanc] from an ancestral population of size [Nanc]. At time [tgst] Population 2[ns] and Population 4[gst] have diverged. At time [taus], there has been an admixture event between the popualtion 2[ns] and the 'ghost' population 4[gst] giving birth to an admixed population 1[aus] with effective size NBaus at time [tBaus], due to a bottleneck lasting a given number of generations, and with an admixture rate [ra] corresponding to the proportion of genes from Population 2[ns].
- Modelchoice error vs ntrees

![[modelchoice_out_graph_error_versus_ntrees 2.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/edentula_pool_A_v3.JPG)

### Scenario Tournament: *C. edentula* Model 2 Pool A vs Model 4 Pool B<a name="edentula_tourn_28"></a>
- Two scenarios: 
	1. scenario 2 from Pool A
	2. scenario 4 from Pool B
###### SIMULATION SETTINGS:
- 50,000 simulations (200,000 per scenario for model choice + 10,000)
	- Start: 1345 28APR23
	- End: 2244 28APR23
	- Duration: 8 hours and 59 minutes.
###### RESULTS:

![[Pasted image 20230429084106.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230429084106.png)

Model 1 (Scenario 2 pool A) selected

In *C. edentula* the most strongly supported scenario involved the bottlenecked founding of the Australian cluster by divergence from the Nova Scotian cluster with a posterior probability (PP) of ~0.68. 

## 29APR23
### Parameter Estimation: *C. edentula* Scenario 2 Pool A<a name="edentula_pe_29"></a>
#### FILE: [edentula_scenario2A_parameter_est](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est)
- 100,000 simulations under the scenario of interest are needed for parameter estimation.
- I will run this in a new project that just contains one scenario, scenario 2 Pool A.
- Condition NBaus< Nns added to prior conditions. The bottlenecked effective population cannot be larger than the source population.
###### SIMULATION SETTINGS:
- 200,000 simulated datasets
- 1 scenario
	- Start: 0852 29APR23
	- End: 0854 30APR23
	- Duration: 25 hours and 2 minutes

## 30APR23

## 01MAY23

### Parameter Estimation: *C. edentula* Scenario 2 Pool A<a name="edentula_pe_30"></a>
- Number of trees: 1000

### Ancestral Effective Population (Nanc)
#### FILE: [edentula_param_est_Nanc](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_Nanc)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2 (Pool A)
- Parameter: Nanc
- Number of oob testing samples = 1000
	- Start: 1100 30APR23
	- End: 1225 30APR23
	- Duration: 1 hour and 25 minutes

###### RESULTS:
- Expectation: 739.613

![[Pasted image 20230430123107.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230430123107.png)

###### INTERPRETATION:
- The effective population of the ancestral *C. edentula* has a median value of 596 and a 90% confidence interval that ranges from 59 to 1858, with the lower and upper bounds corresponding to the 0.05 and 0.95 quantiles, respectively.
---

### Australian Effective Population
###### FILE: [edentula_param_est_Naus](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_Naus)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Naus
	- Start: 1235 30APR23
	- End: 1430 30APR23
	- Duration: 1 hour and 55 minutes
###### RESULTS:
- Expectation: 6509.83

![[Pasted image 20230430150650.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230430150650.png)

###### INTERPRETATION:
- The effective population of the Australian *C. edentula* has a median value of 6780 and a 90% confidence interval that ranges from 2509 to 9789.
- ## Why is this so high relative to the native populations?
- Rosinger et al. 2022, p. 39:
> "Higher selfing rates in C. edentula would be expected to reduce the effective population size compared to the largely self-in- compatible C. maritima (Pollak, 1987)." 
- Rosinger et al. 2022, p. 43
>"A greater fixation rate of weakly deleterious alleles is predicted in the C. edentula due to its higher level of inbreeding, and indeed, the low levels of genetic variability in this species relative to C.  maritima support a lower effective population size in this species."

---


### Bottlenecked Australian Effective Population
#### FILE: edentula_param_est_NBaus(https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_NBaus)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: NBaus
	- Start: 1508 30APR23
	- End: 1650 30APR23
	- Duration: 1 hour and 42 minutes
###### RESULTS:
- Expectation: 39.2744

![[Pasted image 20230430171423.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230430171423.png)


###### INTERPRETATION:
-  The effective population of the bottlenecked Australian *C. edentula* has a median value of 15 and a 90% confidence interval that ranges from 3 to 69.
---

### Great Lakes Effective Population
###### FILE: [edentula_param_est_Ngl](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_Ngl)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Ngl
	- Start: 1715 30APR23
	- End: 1834 30APR23
	- Duration: 1 hour and 19 minutes
###### RESULTS:
- Expectation: 997.109

![[Pasted image 20230430190640.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230430190640.png)

###### INTERPRETATION:
- The Great Lakes effective population has a median value of 914 and a 90% confidence interval that ranges from 298 to 1903.
---


### Nova Scotia Effective Population
#### FILE: [edentula_param_est_Nns](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_Nns)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: Nns
	- Start: ~1900 30APR23
	- End: 2017 30APR23
	- Duration: 1hrs 17min
###### RESULTS:
- Expectation: 
- 1562.72

![[Pasted image 20230501080053.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230501080053.png)

###### INTERPRETATION:
- The Nova Scotian effective population has a median value of 1,273 and a 90% confidence interval that ranges from 500 to 3562. 
---
01MAY23
### Time of Divergence b/n Nova Scotia and Great Lakes
#### FILE: [edentula_param_est_tanc](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_tanc)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: tanc
	- Start: 0802 01MAY23
	- End: 0927 01MAY23
	- Duration: 1 hour and 25min
###### RESULTS:
- Expectation: 4979.95

![[Pasted image 20230501094213.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230501094213.png)

###### INTERPRETATION:
- The Nova Scotian and Great Lakes populations of _C. edentula_ diverged approximately 2,963 years ago (assuming one generation per year). The 90% confidence interval for this estimate ranges from 721 to 7,837 years ago.
---


### Time of Divergence b/n Nova Scotia and Australia
#### FILE: [edentula_pool_A_param_est_taus](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_taus)
###### RF ANALYSIS SETTINGS: 
- Number of trees = 1000
- Scenario: 2
- Parameter: taus
	- Start: 0943 01MAY23
	- End: 1207 01MAY23
	- Duration: 2 hours and 24 minutes
###### RESULTS:
- Expectation: 165.746

![[Pasted image 20230501121344.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230501121344.png)

###### Interpretation:
- Assuming one generation per year for *C. edentula*, the Nova Scotian and Australian populations diverged a median of 166 years ago, with a 95% confidence interval of 157-175 years ago.
---


### Duration of Bottleneck in Australia
#### FILE: [edentula_param_est_tBaus](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_scenario2A_parameter_est/edentula_param_est_tBaus)
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 2
- Parameter: tBaus
###### RESULTS:
- Expectation: 108.152

![[Pasted image 20230501143642.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230501143642.png)

###### INTERPRETATION:
- Assuming one generation per year for *C. edentula*, the novel Australian population was bottlenecked for 111 years, with 95% confidence interval of 46-157 years ago.
---

### Parameter Estimation Interpretation
- Stone 2017 "Parameter estimates are presented as median values (with 95% confidence intervals in brackets)"
- Need to compare summary statistics values predicted by the model and those observed by Rosinger et al. 2022.

## 05MAY23
### Dataset Simulation: *C. maritima* Pool A<a name="maritima_sim_05"></a>
#### FILE:[maritima_pool_a_cont_1](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_pool_a_cont_1)
- Rosinger et al. 2022:
>"Cakile maritima reached western North America in 1935 at Stinson Bay (close to San Francisco), and was first observed sympatric with C. edentula (Barbour & Rodman, 1970)"
- 2019-1935 = 84, [84-104]

### Maritima scenarios
- Saved as: maritima_pool_A
- Using FILE: Cakile_e-Admixture_maritima_abc_test.DIYABC
- 9 scenarios: see 'Scenarii_maritima' tab in 'Scenarii' workbook for details

![[Pasted image 20230508130359.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230508130359.png "maritima Pool A scenarios")

###### CONDITIONS:
```
tanc>tgst
tanc>twna
tanc>tBwna
tgst>twna
tgst>tBwna
twna>tBwna
Nmd>NBwna
Nbl>NBwna
Ngst>NBwna
```
###### SIMULATION SETTINGS:
- 9 scenarios, 200,000 simulated datasets
	- Start: 1336 05MAY23
	- End: 2005 08MAY23
	- Duration: 2 days, 6 hours, and 29 minutes.

## 06MAY23

## 07MAY23

## 08MAY23
### Scenario Choice: *C. maritima* Pool A<a name="maritima_sc_08"></a>
#### FILE: [maritima_pool_A_scenario_choice](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_pool_a_cont_1/maritima_pool_A_scenario_choice)

![[Pasted image 20230511200816.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230511200816.png)

###### RF Analysis Settings:
- 1000 trees
	- Start 2007 11MAY23
	- End 0938 11MAY23
	- Duration:
	
###### RESULTS:

![[Pasted image 20230511213853.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230511213853.png)

## 09MAY23
### Developing Scenario Pool C<a name="scenario_pool_c"></a>
- Should two sets of maritima admixture scenarios be separated into pool B and Pool C? Pool B with pre-introduction admixture and Pool C with post-introduction admixture?
- # Error. You need to run edentula pool B scenarios again.
	- # Why?
	- For the edentula scenarios you constrained the window of time in which admixture to occur to between 156 and 176 years.
	- This means that the admixture event either happened only immediately prior to transportation to Australia or immediately prior (within a 20 year window)
	- You already had the solution to this, pre-introduction admixture was meant to be set to the parameter [tadm] with a U[177-10,000]. This would have allowed admixture to have occurred in the native range up until the divergence event that split away part of a population to Australia.
- # Note:
- For the edentula admixture scenarios you are only really saying that the admixture occurs between 156 and 176 years ago - that is that the admixture only occurred within the window of time the plant was recorded in Australia (so these are post-introduction admixture events that you are testing, not admixture prior to arrival in Australia) <- is that what you wanted to test? Because our prior belief was that there was only a single introduction of edentula and this tests that there were multiple introductions from different populations that then admixed <- also it doesn't really test that there were multiple introductions from the same source population at different points in time (are these capture by Pool A's single introduction scenarios?)
- Note on the above. Yes the scenarios for edentula are that there were separate populations in Nova Scotia, Great Lakes and Ghost and that within the 20 year window of the discovery of edentula in Australia, these separate populations may have been combined/admixed in Australia, resulting in a new, admixed population to be created in Australia. The admixture event occurs within the same 'window of time' as the divergence event. What *Should* have been included here is that population bottlenecks should have been introduced for the entirety of this window of time: ie. diverge from source (156-176 years ago) -> bottleneck (0-20 years long) -> admixture (156-176 years ago) -> bottleneck (0-176 years long)


## 10MAY23


## 11MAY23 




## 12MAY23
Dataset Simulation: *C. maritima* Pool C<a name="maritima_sim_12"></a>
#### FILE: [edentula_pool_C](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_pool_C)
###### CONDITIONS:
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
###### SIMULATION SETTINGS:
Start: 1519 12MAY23
End:  paused 1617 12MAY23 - need to prioritise simulation of C. edentula Pool C

###### SIMULATION SETTINGS:
- 200,000 to get at least 20,000 per scenario
	- Start: 1623 12MAY23
	- End: 10:55 13MAY23
	- Duration: ~19 hours

#### Poster:
Introduction, aims, methods, results, conclusion written.


## 13MAY23
#### Poster
0300 Poster work


### Scenario Choice: *C. edentula* Pool C<a name="edentula_sc_13"></a>
#### FILE: [edentula_pool_C_model_choice](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_pool_C/edentula_pool_C_model_choice)
- 1000 trees
	- Start: 1428 13MAY23
	- End: 1537 13MAY23
	- Duration

###### RESULTS:

![[Pasted image 20230513153834.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230513153834.png)

Selected model 6 with PP 0.606

![[Pasted image 20230513154019.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230513154019.png)

At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[ns],  pop3[gl] and pop6[gst3] split. At time [taus] pop4 [gst1] splits off pop6[gst3] and is bottlenecked for time [tBaus] resulting in Ne of [NBgst1]. Later (more recently) at time [tBaus2] pop 5[gst2] splits off pop6[gst3] and is bottlenecked for time [tBaus2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop1 [aus] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra]. 
#### Interpretation: very interesting, would have thought that it would have picked something more closely related to Nova Scotia


### Scenario Tournament: *C. edentula*<a name="edentula_tourn_13"></a>
#### FILE: [edentula_A_B_C](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_A_B_C)
- Three scenarios: 
	1. scenario 2 from Pool A
	2. scenario 4 from Pool B
	3. scenario 6 from Pool C

###### CONDITIONS:
```
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
###### SIMULATION SETTINGS:
- 50,000 simulations (20,000 per scenario for model choice + 10,000)
	- Start: 1619 13MAY23  [ CRASH ] reset 1658 13MAY23
	- End: 2302 13MAY23
	- Duration:

### Scenario Choice: *C. edentula* Pool ABC 
#### FILE: (https://github.com/samuel-craig/ABC_cakile/tree/main/Output/edentula_A_B_C/edentula_pool_ABC_scenario_choice)
###### RF Analysis Settings:
- Run 1000 trees
	- Start 2306 13MAY23
	- End:23:56 13MAY23
	- Duration: 56 minutes

###### RESULTS:

![[Pasted image 20230513235709.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230513235709.png)

### Poster
- 2230: Completed phylogeny photograph diagram for Poster


## 14MAY23
### Poster
Diagram in Adobe Illustrator, composite image Photoshop

## 15MAY23
### Poster
Poster completion, submission 1837 15MAY23
#### FILE: [POSTER](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/BIO3990_poster_samuel_craig_32183720.pdf)

## 16MAY23
### Dataset Simulation: *C. maritima* Pool C<a name="maritima_sim_16"></a>
#### FILE: [maritima_pool_c](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_pool_c)
- Resume: maritima pool C simulation
- Load from existing project 'maritima_pool_c'
	- headerRF.txtx
	- statobsRF.txt
	- reftableRF.bin

![[Pasted image 20230516080750.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230516080750.png)

###### SIMULATION SETTINGS:
- Simulations: 200,000
	- Start 0808 16MAY23
	- End: 1502 18MAY23
	- Duration: 30 hours, 55 minutes


### Scenario Choice: *C. Maritima* Pool C<a name="maritima_sc_16"></a> 
#### FILE: [maritima_pool_c](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_pool_c/maritima_pool_C_scenario_choice)
###### RF Analysis Settings:
- Number of trees: 1000
	Start: 1635 18MAY23
	End: 1711 18MAY23
	Duration: 36 minutes

###### RESULTS:

![[Pasted image 20230523085014.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230523085014.png)

Model 4 chosen, very slim margin between models 4, 9, 5 and 6

###### MODEL IMAGE:

![[Pasted image 20230524143913.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230524143913.png)

###### MODEL DESCRIPTION:
At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[med],  pop1[balt] and pop6[gst3] split. At time [twna] pop4 [gst1] splits off pop6[gst3] and is bottlenecked for time [tBwna] resulting in Ne of [NBgst1]. Later (more recently) at time [tBwna2] pop 5[gst2] splits off pop1[balt] and is bottlenecked for time [tBwna2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop3 [wna] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra].

## 20MAY23
### Dataset Simulation: *C. maritima* pool B<a name="maritima_sim_20"></a> 
###### CONDITIONS:
```
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
```
Changed Pool C to reflect the possibility of pre-invasion admixture, allowing admixture to occur prior to likely invasion time [105-10,000].

###### SIMULATION SETTINGS:
	- Start: 2132 20MAY23
	- End: 1939 22MAY 23
	- Duration: 46 hours, 7 minutes
	
## 22MAY23
### Scenario Choice: *C. maritima* Pool B<a name="maritima_sc_22"></a>
#### FILE: [maritima_pool_B_scenario_choice](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_pool_B/maritima_pool_B_scenario_choice)
![[Pasted image 20230522194550.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230522194550.png)

###### RF Analysis Settings:
- 5 noise variables
- 1000 trees
	- Start: 1946 22MAY23
	- End: 2041 22MAY 23
	- Duration: 55 minutes

###### RESULTS:

![[Pasted image 20230523084808.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230523084808.png)

Model 1 selected by only 1 vote.

## 23MAY23
### Scenario Tournament: *C. maritima*<a name="maritima_tourn_23"></a>
#### FILE: [maritima_A_B_C](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_A_B_C)
Tournament between winners (and scenarios within 10 votes of the winning scenario - too close to differentiate) of poll A, B, C

1. Scenario 2 Pool A;
2. Scenario 1 Pool B;
3. Scenario 2 Pool B;
4. Scenario 4 Pool C;
5. Scenario 5 Pool C;
6. Scenario 6 Pool C;
7. Scenario 9 Pool C;

![[Pasted image 20230523090507.png]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/Pasted%20image%2020230523090507.png)

###### SIMULATION SETTINGS:
- Same priors as per each Pool's individual priors
- Conditions in spreadsheet, tab 'Priors_maritima'
- 150,000 datasets (at least 20,000 per scenario)
	- Start: 0932 23MAY23
	- End: 0712 25MAY23
	- Duration: 1 day, 21 hours, 40 minutes.

## 25MAY23
### Scenario Choice: *C. maritima*<a name="maritima_sc_25"></a>
#### FILE: [maritima_A_B_C_scenario_choice](https://github.com/samuel-craig/ABC_cakile/tree/main/Output/maritima_A_B_C/maritima_A_B_C_scenario_choice)
###### RF ANALYSIS SETTINGS: 
- <28,000 datasets per scenario
- 2000 trees
	- Start: 0939 25MAY23
	- End: 1038 25MAY23
	- Duration: 59 minutes

###### RESULTS:

![[maritimatourn]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/lasttourn.JPG)


###### MODEL IMAGE:

![[PoolCmodel4.jpg]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/DIYABC_screengrabs/PoolCmodel4.JPG)

###### MODEL DESCRIPTION:
At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[med],  pop1[balt] and pop6[gst3] split. At time [twna] pop4 [gst1] splits off pop6[gst3] and is bottlenecked for time [tBwna] resulting in Ne of [NBgst1]. Later (more recently) at time [tBwna2] pop 5[gst2] splits off pop1[balt] and is bottlenecked for time [tBwna2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop3 [wna] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra].


### Parameter Estimation: *C. maritima*<a name="maritima_pe_25"></a>
#### FILE: [maritima_scenario4C_param_est]()
###### SIMULATION SETTINGS:
-  100,000 simulated datasets
-  Conditons as per 'Priors_maritima tab' in 'Scenarii' Spreadsheet
- 1 scenario
	- Start: 1719 25MAY23
	- End: 1518 26MAY23
	- Duration: ~22 hours

## 26MAY23

---

#### Ancestral Effective Population
###### FILE: [maritima_param_est_Nanc]
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nanc 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 1 Bottlenecked Effective Population
###### FILE: [maritima_param_est_NBgst1]
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: NBgst1 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 1 Bottlenecked Effective Population
###### FILE: [maritima_parameter_est_NBgst2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: NBgst2 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Baltic Effective Population
###### FILE: [maritima_parameter_est_Nbl] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nbl 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 1 Effective Population
###### FILE: [maritima_parameter_est_Ngst1] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst1
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 2 Effective Population
###### FILE: [maritima_parameter_est_Ngst2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION


## 27MAY23
---

### Ghost 3 Effective Population
###### FILE: [maritima_parameter_est_Ngst3] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst3
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---


### Mediterraanean Effective Population
###### FILE: [maritima_parameter_est_Nmd] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nmd
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Western North American Effective Population
###### FILE: [maritima_parameter_est_Nwna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nwna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Rate of Admixture
###### FILE: [maritima_parameter_est_ra] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: ra
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Ancestral Population Divergence
###### FILE: [maritima_parameter_est_tanc] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tanc
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time/Duration of Bottlneck in Western North America (initial introduction)
###### FILE: [maritima_parameter_est_tBwna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tBwna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time/Duration of Bottlneck in Western North America (secondary introduction)
###### FILE: [maritima_parameter_est_tBwna2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tBwna2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Post-Introduction Admixture
###### FILE: [maritima_parameter_est_tpost] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tpost
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Western North American divergence (initial introduction)
###### FILE: [maritima_parameter_est_twna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: twna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Second Western North American divergence (secondary introduction) 
###### FILE: [maritima_parameter_est_twna2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: twna2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

- Parameter estimation, *C. maritima* scenario 4, Pool C, complete 1931 27MAY23.






## 09JUL23
### Updating Log: June - July<a name="Updating_log_Jun_Jul"></a> 
< 09JUL23
#### *C. edentula*
- M3 used to generate datasets from a run of all 25 *C. edentula* scenarios at once IOT improve overlap between simulated and observed data (in LDA plots) and reduce overall prior error. Datasets of 500,000 and 1,000,000 were generated and model choice conducted with 10,000 trees, with the same result and marginal difference in prior error, but both with greatly improved LDA plots.
- See confusion tables, LDA, and scenario diagram:
1. *C. edentula* pooled scenarios
2.  1,000,0000 datasets, all *C. edentula* scenarios
3.  500,000 datasets, all *C. edentula scenarios, extended priors


#### 1. *C. edentula* pooled scenarios:
[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_A_B_C_v.2/edentula_A_B_C_v.2_scenario_choice/modelchoice_out.confusion)

![[LDA]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_A_B_C_v.2/edentula_A_B_C_v.2_scenario_choice/modelchoice_out_graph_lda.png)

[Model Choice Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_A_B_C_v.2/edentula_A_B_C_v.2_scenario_choice/modelchoice_out.predictions)
Note: Scenario 8 is *C. edentula* scenario 23.

![[Scenario Diagram]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_all_scenarios_v.1/Scenario_23_edentula.png)

Description: At time [tanc], which has a effective population [Nanc], pop2[ns] and pop3[gl] split. At time [taus] pop 4 [gst1] splits off pop2[ns] and is bottlenecked for time [tBaus] resulting in Ne of [NBgst1]. Later (earlier) at time [tBaus2] pop 5 [gst2] splits off pop2[ns] and is bottlenecked for time [tBaus2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop1 [aus] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra]. 

#### 2. *C. edentula* all scenarios, 1,000,0000 datasets, 10,000 trees:

[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_all_scenarios_v.1/modelchoice_out.confusion)

![[LDA]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_all_scenarios_v.1/LDA_plot_edentula_all_scenario.png)

[Model Choice Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_all_scenarios_v.1/modelchoice_out.predictions)

![[Scenario Diagram]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_all_scenarios_v.1/Scenario_23_edentula.png)

Description: At time [tanc], which has a effective population [Nanc], pop2[ns] and pop3[gl] split. At time [taus] pop 4 [gst1] splits off pop2[ns] and is bottlenecked for time [tBaus] resulting in Ne of [NBgst1]. Later (earlier) at time [tBaus2] pop 5 [gst2] splits off pop2[ns] and is bottlenecked for time [tBaus2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop1 [aus] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra]. 

#### 3. 500,000 datasets, all *C. edentula scenarios, extended priors

[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_extended_priors/edentula_extended_priors_model_choice/modelchoice_out.confusion)

![[LDA]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_extended_priors/edentula_extended_priors_model_choice/modelchoice_out_graph_lda.png)

[Model Choice Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_extended_priors/edentula_extended_priors_model_choice/modelchoice_out.predictions)

![[Scenario Diagram]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_extended_priors/edentula_extended_priors_model_choice/Scenario_25_edentula.png)

Description: Same as scenario 5 but now diverge from population 2[ns] earlier (pop5[gst2] diverges from pop6[gst3] later). In the figure it appear like pop3[gl] emerges from pop6[gst3] but the lines are just lying ontop of each other. Pop3[gl] isnt involved in this scenario at all.

(Scenario 5) At time [tanc], there is an ancestral population which has a effective population [Nanc], pop2[ns],  pop3[gl] and pop6[gst3] split. At time [taus] pop4 [gst1] splits off pop3[gl] and is bottlenecked for time [tBaus] resulting in Ne of [NBgst1]. Later (more recently) at time [tBaus2] pop 5[gst2] splits off pop6[gst3] and is bottlenecked for time [tBaus2] resulting in a Ne of [NBgst2]. Then at time [tpost] pop1 [aus] is given rise to from the admixture of pop5[gst2] and pop4[gst1] at a rate of [ra]. 


Note: the scenario chosen in the extended priors only differed from scenario 23 by having one ghost population branch off Nova Scotia, as opposed to two ghost populations branching off Nova Scotia - as in scenario 23. Extending priors did not dramatically reduced prior error rate.

---

### Next steps 09JUL23
- Need to decide whether to continue with parameter estimation on scenario 23 for *C. edentula* or re-run pool A (the pool with the lowest prior error, good LDA overlap and highest posterior probability) on M3
- This seems like an important next step ^, re-run pool A on M3, 1,000,000 datasets, 10,000 trees.

---
### M3 Procedure
- Using WSL-Ubuntu-22.04 + MobaXTerm
- `ssh ___@m3.massive.org.au`
- om62>diyabc_RF>edentula_all_scenarios_v.4
- [contains .SNP file, headerRF.txt, reftableRF.bin, statobsRF.txt]

Set up slurm session (interactive session)
- `smux new-session --ntasks=20 --time=20:00:00`

Load diyabcRF
- `module load diyabc/v1.1.27`

Generating RNG seed
- `diyabc-RF-linux-v1.1.27 -p ./ -n "t:30"`
- `# diyabc-RF-<os>-<version> -p ./ -n "t:<n_core>"`

Training Set Simulation
- `diyabc-RF-linux-v1.1.27 -p ./ -R "ALL" -m -t 30 -g 50 -r 1000000`
- `# diyabc-RF-<os>-<version> -p ./ -R "ALL" -m -t <n_core> -g <batch_size> -r <n_simu>`


## 10JUL23

### Starting *C. maritima* all scenarios on M3.
File: maritima_all_scenarios_v.1
M3 job ID: _222
Procedure as above

## 12JUL23

### *C. maritima*
- Change job name to __916
- Start new session with increased RAM per CPU ```smux new-session --ntasks=30 --time=24:00:00 --mem=32```


## 14JUL23
### *C. maritima*
- Change job name to 30468618
- Start new session with increased RAM per CPU ```smux new-session --ntasks=30 --time=24:00:00 --mem=64G```
- Good speed of simulation, use these settings.

### *C. edentula* Pool A: Model Choice
- File (om62>diyabc_RF): edentula_all_scenarios_v.4
- Start RF analysis of edentula Pool A simulations
- Again, ```smux new-session --ntasks=30 --time=24:00:00 --mem=64G```
- Job name: 30468626
  
- `module load diyabc/v1.1.27`
- `abcranger-linux-v1.16.44 -t 10000 -j 30`
- 'abcranger-<os>-<version> -t <n_tree> -j <n_core>'
- 30 CPU, 10,000 trees, start 0849 14JUL17

## 15JUL23
- Dataset simulation for *C. maritima* continuning on Job ID: 30503015
- RF analysis/model selection for *C. edentula* pool A continuing on Job ID: 30479624
- Next task: model selection for *C. maritima* <- attempt to use same session running RF analysis on *C. edentula* Pool A
- ^x: instead running *C. maritima* RF analysis on Job ID: 3050315 <- however, RAM / time of session may be insufficient.
- Closing session 30503015 opening new: `smux new-session --ntasks=30 --time=2-00:00:00 --mem=64G` Job ID: 30505089, waiting for connection.


## 17JUL23
- Simulations complete.<a name="#JUL_simulations"></a>

### *C. edentula* Pool A
- Saved as "edentula_all_scenarios_v.4" (<- but is actually just Pool A) in om62

- Prediction file Using M3, 4 x 10^4 per scenario
-         model1        model2        model3        model4        model5        model6        model7        model8        model9 selected model  post proba
          1611          2718            59           902           794            48           853          2736           279              8       0.618
![[Scenario Diagram: *C. edentula, Pool A, scenario 2]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_all_scenarios_v.4/edentula_pool_A_scenario_8.png)


- Prediction file Using M3, 2 x 10^4 per scenario
-          model1        model2        model3        model4        model5        model6        model7        model8        model9 selected model  post proba
           162           259            11            95           103             2            96           246            26              2       0.630
![[Scenario Diagram: *C. edentula, Pool A, scenario 2]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_A/edentula_pool_A_scenario_choice/edentula_Pool_A_scenario_2.png)

   
- Note: the only difference between scenario 2 and scenario 8 in edentula pool A is the presence of a ghost population diverging from Nova Scotia sometime prior to the invasion of Australia (prior interval allows paramter tgst to vary between 177-10,000 years ago.) Does this imply the presence of a unsampled/ghost population in Nova Scotia? What we can say is that in either case, the scenario selected always involves an invasion consisting of a population of Nova Scotian origin.
- Simulations showed almost identical overall prior error rate whether conducted with 4 x 10^4 (0.192751) or 2 x 10^4  datasets per scenario (0.19569).
- However class-specific error rates were higher using 2 x 10^4 per scenario.
- Model 2 (selected under the 2 x 10^4  datasets per scenario) has a class-specific error rate of ~23%, while scenario 8 (selected under the 4 x 10^4 datasets per scenario) has a class-specific error rate of ~3%
----
- 2 x 10^4 per scenario
[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_A/edentula_pool_A_scenario_choice/modelchoice_out.confusion) 
----
- 4 x 10^4 per scenario
[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/edentula_all_scenarios_v.4/modelchoice_out.confusion) 
----
- Does this mean we are able to rely/trust the predictions made by the simulation with lower class-specific error rate?
- Next steps, *C. edentula*:
1. Graph the LDAs for both simulations and compare.

![[LDA plot, edentula scenario 8, 4 x 10^4 per scenario]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_all_scenarios_v.4/edentula_pool_A_model_choice_8_v.1.png)

Fig.x LDA plot, edentula scenario 8 predicted, 4 x 10^4 per scenario

![[LDA plot, edentula scenario 2, 2 x 10^4 per scenario]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/edentula_A/edentula_pool_A_model_choice_8_v.2_20K_per_scen.png)

Fig.x LDA plot, edentula scenario 2, 2 x 10^4 per scenario

2. Determine whether error (prior and class-specific are low enough to move forward with parameter estimation).
- unanswered, consult papers re: level of priors they accepted
- Moving forward with new dataset simulation for parameter estimation of scenario 8
- Job ID: 30522154
- Parameter estimation requires 10^5 datasets simulated.
- File name: `edentula_pool_A_param_est_m3`



### *C. maritima* All scenarios
- Prediction file, using M3, 4 x 10^4 per scenario
-         model1        model2        model3        model4        model5        model6        model7        model8        model9       model10       model11       model12       model13       model14       model15       model16       model17       model18       model19       model20       model21       model22       model23       model24       model25 selected model  post proba
           113           474           113           139           320            70           277           192           133           248           166           182           132           107           147           175           166          1190          1220           812           782           263           789           939           851             19       0.492

![[*C. maritima*, scenario 19]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/maritima_all_scenarios_v.1/maritima_scenario_19.png)

Note: scenario 18 (runner up to scenario 19) is almost identical to scenario 19, except with the order of the ghost populations reversed.

[Confusion Table](https://github.com/samuel-craig/ABC_cakile/blob/main/Output/maritima_all_scenarios_v.1/modelchoice_out.confusion)

![[LDA plot]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/maritima_all_scenarios_v.1/maritima_all_scenario_model_choice_19_v.1.png)

Selected model 19 is in green, non-transparent. Observed data in dark blue.

- For *C. maritima* all scenarios, both the overall prior error rate, and the class-specific error rates for the simulation appear very high - likely too high to say anything meaningful if we were to estimate paramters.
- Next steps *C. maritima*
- Looking at the initial simulations by pool, *maritima* pool A showed the lowest overal prior error (0.16434) however, just like in the *edentula* pool A scenarios, the lowest class-specific errors came from scenarios with similar topologies that inserted a ghost population between the source population and the invasive population. Does this extra ghost population contrivance allow the analysis greater flexibility and make the error rate lower? Would additional ghost populations added to the topologie make the class-specific error even lower as the analysis can use these as a kind of placeholder/wildcard? <- e.g. fill the gap but is not acutally based on any observation?
- Additionally, Pool A *maritima* scenarios showed a poor correspondence between observed and simulation data in their LDA graph.
1. Graph the LDAs for *maritima* all scenarios and compare (see above).
2. Consider running a *maritima* extended priors scenario, as was done with *edentula* to see whether prior error (or LDA correspondence) is reduced.
3. Consider using pseudo-observed-datasets (PODs) to generater a baseline for what is the expected result of a given scenario.
4. Review clustering approach, could diyabc be struggling to resolve due to there being more/less clusters than expected?
	- Consider Stone et al on bitou bush, could the wNA population be clustered any differently?
 	- What were the cut-offs for inclusion in a cluster, what were the reasons these cut-offs were chosen? Are these fallible?

5. Consider bridgehead invasion. "species more likely to be introduced to, and spread from, highly connected hubs" Bertelsmeier and Keller (2018).
	- For *C. edentula* this would involve including the invasive Western North American population as the source of the invasion of Australia by *C. edentula*.
 	- For *C. maritima* this would involve including the invasive Australia population of *C. maritima* as the source of the invasion of WNA by *C. maritima*.
	- Justification(?): sequential gold rushes, starting in WNA, then being rapidly followed by Australia may have meant that Victoria and San Francisco formed a highly connected hub sometime around 1849.

## 18JUL23
### *C. edentula* Pool D
- Pool B is a consideration of bridgehead introduction on *C. edentula*'s invasion of Australia. The scenarios were adapted from van Boheemen et al 2017. All scenarios in Pool D begin with a polytomy between the Nova Scotian, Great Lakes and Western North American *C. edentula*. This is because, in lew of any insight into the source of Western North American *C. edentula* or it's hybrid status, this was necessary to reduce the number of scenarios considered. As far as the distant past is concerned the scenarios treat the origin of the Western North American *C. edentula* as simultaneous to the split between the Great Lakes and Nova Scotia populations.
- Additionally, no attempt has been made to determine the presence of a bottleneck in the Western North American *C. edentula*. This is not the target.
- Using the method above (start of log) samples where filtered for cluster and monomorphic loci. Elements are shown below:
- create keep file "keep_edentula_incl_wna.txt"

- Filtering using ID file
`/mnt/c/Users/___/Documents/Monash/BIO3990$ bcftools view -S keep_edentula_incl_wna.txt Cakile_e-Admixture_downsampled17721_rn_poly > Cakile_edentula_incl_wna`  

- Checking rows match between sample ID file and remaining file:
`bcftools query -l Cakile_edentula_incl_wna | wc -l` 154           

- Before filtering for monomorphic: `bcftools view -H  Cakile_edentula_incl_wna | wc -l`     10000  

- After filtering for monomorphic: `bcftools view -H  Cakile_edentula_incl_wna_abc | wc -l` 5105          

- Convert to SNP, follow instructions in log (above), don't forget to include entire path to file:  

`/mnt/c/Users/___/Documents/Monash/BIO3990/Cakile_edentula_incl_wna_abc.vcf`

`/mnt/c/Users/___/Documents/Monash/BIO3990/diyabc2vcf_edentula_wna.txt`

- Output:
`Cakile_edentula_incl_wna_abc.DIYABC.snp`

- Dataset simulation, n = 350K - at least 20K per scenario. M3, 30 cores, 64G per core, start 1028 18JUL23
- `Job ID  Job Name`
- `30522154        interactive_session`

RF: Model Choice:
- `abcranger-linux-v1.16.44 -t 5000 -j 30`
- 5000 trees because, reaistically, error begins to fall off well before 1000 trees.



### *C. edentula* Pool A, scenario 8, parameter estimation
- 10 x 10^4 new datasets simulated for use in parameter estimation.
- Parameter estimation will continue only after dataset simulation and model choice has been conducted for *C. edentula* pool D. If a scenario in Pool D fits the data better, the estimation of parameters from the winning scenario in Pool A will be a waste.


### *C. maritima* extended priors
- In lew of having the Australian *C. maritima* data to create a bridgehead pool, testing whether widening the priors for *C. maritima* is the next simulation to be conducted.
- See extended priors in excel sheet for details
- `Job ID  Job Name`
- `30535597        interactive_session`
- `diyabc-RF-linux-v1.1.27 -p ./ -R "ALL" -m -t 30 -g 50 -r 500000` <- at least 25,000 per scenario, may need 10K more to make sure. 

## 21JUL23
### *C. edentula* Pool D
        model1        model2        model3        model4        model5        model6        model7        model8        model9       model10       model11       model12       model13 selected model  post proba
           464           405            17           620           322            80           968            78           897             6           152           119           872              7       0.646
- Surprisingly(?) *C. edentula* Pool D, scenario 7, showed the highest posterior probability of any of the *C. edentula* Pools.
- Is this simpply because of the inclusion of thw Western North American *C. edentula*? That it is more confident because it has a new population, greater SNPs, and a place to place them within the scenarios? -> new Psuedo-Observed Datasets (PODs) to check this behaviour.
However, *C. edentula* Pool D included scenatios that were similar to pools A, B, C. Scenario 2 in Pool D ("Single Origin: Nova Scotia") is not fundamentally different from Scenario 2 in Pool A, and Scenario 8 in Pool A is the same as Scenario 2 in Pool A except with an interceding unsmapled popualtion between the source and invaded ranges. Yet of the top three scenarios in *C. edentula* Pool D, 7D (1st) involves initial introduction from Nova Scotia followed by a secondary introduction from Western North America, 9D (2nd) involves an initial introduction from Western North America, followed by a secondary introduction from Nova Scotia, and 13D (3rd) involves initial AND secondary introductions from Western North America. Only the 6th most supported scenario only includes a single introduction from Nova Scotia - which is the winning scenario under the Pool A scenario simulations (named "edentula_all_scenarios_v.4") and the 7th most supported involves initial and sceondary introductions from Nova Scotia - which is the winning scenario under the "All scenarios" simulations.
- Additionally, as secondary introduction priors were allow to go to 0, until parameter estimation is conducted we don't know whether these secondary introductions are >0 and thus exist (but it seems as though they would otherwise the single introduction scenarios would surely recieve more support.)
#### Next Steps: *C. edentula* Pool D
- Check Hanna's population structure analysis, is there any plausible possibility that Western North America *C. edentula* could contribute to the Australian *C. edentula*. In particular answer the following:
1. When did *C. edentula* reach Western North America? What is the strength of the evidence/how sure are we in this estimation?
2. When did *C. edentula* reach Australia? What is strength of the evidence/how sure are we in this estimation?
3. Do the admixture results support this sequence of events? If not, why? What is th strength of the evidence for not considering Western North American *C. edentula* as a source for the Australian introduction?
 
 - Pseudo-Observed Datasets (PODs): does adding more populations inherently increase the posterior probability of the RF model choice analysis?
 - Classification error is not as low as in Pool A scenario simulations (named "edentula_all_scenarios_v.4"), Scenario 8, what - precisely - does classification error tell us?
 - LDA plots showed observed data was not in the centre of the simulated data of scenario 7, and that scenario 7, 9, and 13 each overlapped under the observed data. What is causing this imprecision, is it that all source populations in Pool D diverge from the ancestral population simulatenously as a polytomy? Would having the Western North American *C. edentula* diverge *later* than the Nova Scotian and Great Lakes *C. edentula* result in lower prior and class errors? or does that fact that the polytomy 'motif' is repeated in each scenatio 'cancel-out' its effect (may not cancel out, but may create a higher baseline of classification error).
 - Additionally need to consider the issue of resolution. High classification error may point to diyabc being unable to resolve between scenarios, and in Pool D the lowest classification error (2%) was held by the 5th most voted scenario (1D) which was 4-way polytomy scenario in which wNA, Nova Scotia, Great Lakes and Australian *C. edentula* all simulatenously diverged from an ancestral population.

 ![[scenario and LDA plot]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/Figures/Pool_D_comparisons_1.JPG)

 
 ![[scenario and LDA plot]](https://raw.githubusercontent.com/samuel-craig/ABC_cakile/main/Output/Figures/Pool_D_comparisons_2.JPG)

 Fig.x: This a a qucik side by side comparsion of the winning scenarios in each Pool, the second image being of the 'runner-up' scenarios of Pool D, as well as scenario 2 (6th most votes) which I though would have been the favoured scenario based on the previous *C. edentula* results. Note, Great Lakes population has been blanked out for simplicity.
 
### Pool D is moot, it is out of chronological sequence that *C. edentula* was in WNA before it was in Australia. Barbour and Rodman 1970 illustrate that it's earlier confirmed appearance in WNA was not before 1880, some 20 to 40 years later than *C. edentula* being thought to be in Australia. The only way around this would be to cast doubt on the comprehensiveness of two expeditions in the area in which *C. edentula* was found in California. Even if you checked using approximations of GPS coords where the expeditions collected their specimens and identified a blindspot where *C. edentula* was eventually found, there would be no postive identification of *C. edentula* in California prior to 1882. Thus Pool D is moot and regardless, should have included scenarios that involved the WNA population occuring after the Australian population, rather than all scenarios being the opposite of this.

Next steps:
-Paramter estimation for *C. edentula* Pool A, Scenario 8 could continue. Onbly had a moderate posterior probability, but a very low classification error.

## 22JUL23
*C. maritima* extended priors

	model1        model2        model3        model4        model5        model6        model7        model8        model9       model10       model11       model12       model13       model14       model15       model16       model17       model18       model19       model20       model21       model22       model23       model24       model25 selected model  post proba
             8           355            26            18           160            20            56            91            57           112            54            69            68            39            59            85            79           886           765           222           425            61           468           369           448             18       0.508

Posterior probability is higher than most previous *C. maritima* scenarios (the exception is Pool B), however the prior error rate: 0.441808 is high, as is all scenario's classification error rates.
Ultimately I think we need to test *C. maritima* for bridgehead scenarios, and thus need the Australian *C. maritima* data.


## 25JUL23
### Parameter Estiamtion: *C. edentula* scenario 8 (from Pool A)
#### Effective Population parameters
1. Naus
2. Nns
3. Ngl
4. Ngst
5. NBaus
6. Nanc
#### Time parameters (in generations since present)
1. tBaus
2. taus
3. tgst
4. tanc

Note: for command line
`-t` is number of tree used for RF analysis
`-j` is number of cores used
`--noob` is number of out-of-the-bag error datasets used
`--plsmaxvar` PLS components explaining 95% of variance added to the feature vector

---

#### Naus: Effective population of the comtemporary Australian *C. edentula* populationn
###### FILE: []
###### RF ANALYSIS SETTINGS:
- `abcranger-linux-v1.16.44 -t 1000 -j 30 --parameter Naus --chosenscen 1 --noob 10000 --plsmaxvar 0.95`
###### RESULTS:
- Expectation: 
Parameter estimation (point estimates)
Expectation        Median Quantile_0.05 Quantile_0.95      Variance
7109.69          7344       3306.22          9816   4.36853e+0
  
![[]]()

###### INTERPRETATION

---

### Ghost 1 Bottlenecked Effective Population
###### FILE: [maritima_param_est_NBgst1]
###### RF ANALYSIS SETTINGS:
- 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 1 Bottlenecked Effective Population
###### FILE: [maritima_parameter_est_NBgst2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: NBgst2 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Baltic Effective Population
###### FILE: [maritima_parameter_est_Nbl] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nbl 
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 1 Effective Population
###### FILE: [maritima_parameter_est_Ngst1] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst1
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Ghost 2 Effective Population
###### FILE: [maritima_parameter_est_Ngst2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION


## 27MAY23
---

### Ghost 3 Effective Population
###### FILE: [maritima_parameter_est_Ngst3] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Ngst3
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---


### Mediterraanean Effective Population
###### FILE: [maritima_parameter_est_Nmd] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nmd
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Western North American Effective Population
###### FILE: [maritima_parameter_est_Nwna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: Nwna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Rate of Admixture
###### FILE: [maritima_parameter_est_ra] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: ra
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Ancestral Population Divergence
###### FILE: [maritima_parameter_est_tanc] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tanc
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time/Duration of Bottlneck in Western North America (initial introduction)
###### FILE: [maritima_parameter_est_tBwna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tBwna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time/Duration of Bottlneck in Western North America (secondary introduction)
###### FILE: [maritima_parameter_est_tBwna2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tBwna2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Post-Introduction Admixture
###### FILE: [maritima_parameter_est_tpost] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: tpost
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Western North American divergence (initial introduction)
###### FILE: [maritima_parameter_est_twna] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: twna
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---

### Time of Second Western North American divergence (secondary introduction) 
###### FILE: [maritima_parameter_est_twna2] <- note, parameter_est not param_est
###### RF ANALYSIS SETTINGS:
- Number of trees = 1000
- Scenario: 4C 
- Parameter: twna2
###### RESULTS:
- Expectation: 

![[]]()

###### INTERPRETATION

---






