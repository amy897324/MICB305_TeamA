# MICB305_TeamA
## Oct 1
Does the composition of a patient's microbiome and prevalence of depression in a patient impact their MS severity? 

## Oct 15
Introduction and Background: provides the premise for why/how your dataset was collected in addition to an overview of the studies that have already been conducted on your dataset or relevant to your dataset (consider what you presented for your P2 review oral presentation)

Hypothesis: How does the microbiome of patients as well as the different allergies they have impact the prevalence and severity of MS? We believe that there is a correlation between the microbiome, the MSS severity score, and the different categories of depression listed within the data. In the literature listed below, depression and MS share some biological causative factors (HPA axis for example which may have potential connections to the human microbiome). https://pmc.ncbi.nlm.nih.gov/articles/PMC3181849/

Our dataset was collected from individuals around the world with the aim of finding a connection between MS and the microbiome, specifically how MS affects our microbiome. Participants were recruited via MS clinics around the world. Some studies which have already been conducted on our dataset include (), which focuses on eczema's role in masking the effects of MS on the microbiome as well as….(do we need to find/list them all?). Some studies conducted relevant to our dataset include () and (). Both focus on…

Potential ideas for experimental aim.

Separate microbiomes into groups, in R compare how depressions affect the microbiome.

Test between biodiversity and MSS severity (more or less diversity in different depressions)

Potentially run manova (whichever statistical test is for 3 or more variables).

Questions For Tomorrow:
What do we need to remove from the metadata?
Can you guide us to make a proposal in R after using QIIME2?

## Oct 15 Team notes
Goal for next week: figure out specific research aim

Overall RQ (from first week discussion): 
- Does the composition of a patient's microbiome and prevalence of depression in a patient impact their MS severity? 
- Effects of depression and MSSS on gut microbiome

Hypothesis to connect all 3:
- Hoping to run PERMANOVA to run all 3
- Alpha and beta diversity
- Severe MS associated to higher level/diverse microbiome and depression
- Or microbiome on depression on MS

(NEW RQ IDEA): If you want to connect all 3, do effect of prevalence of depression and MS severity on gut microbiome
- Severe MS (PMS), presence of depression (29)
- Severe MS (PMS), absence of depression (80)
- Less severe MS (RMS), presence of depression (60)
- Less severe MS (RMS), absence of depression (266)
- Healthy, depression (37)
- Healthy, no depression (396)
*Use the different types of MS (SMS, RRMS, PMS) to determine the severity of MS*
Known that PMS is more severe than RRMS
- Best to use original paper to find it
- Sample size of above ~10 is okay to use for research

Rationale of hypothesis (required in proposal): If it does affect gut microbiome, why does it do that
- Worth exploring RF model
- Presence of specific species
- Possibly microbiome diversity
- Can’t predict the general gut microbiome
- If sample size big enough/prevalent for one specific type of MS, can just use that one
- Most common form of MS
- Get sample number (for each of 6 variables above) based on this type of MS

Proposal 
What type of analysis and our approach
How it can contribute to our hypothesis (why this analysis?)
Not required to do actual analysis, just explain why you chose that one
Possibly do QIIME2 processing though
What machinery we’re using
Need to manipulate metadata
Numeric → character
Exclude NAs in depression column

## Oct 22
Introduction

Multiple sclerosis (MS) is a long-term autoimmune disease in which the immune system mistakenly destructs myelin cells, the fatty layer that insulates and shields nerve fibers in the central nervous system (CNS). The demyelination disrupts normal transmission of electrical signals along neurons and results in axonal injury and neuronal loss. With progressive damage, multiple sclerosis contributes to a wide spectrum of neurological symptoms, such as fatigue, vision changes, coordination difficulties, weakness, and memory deficits.

The primary subtypes of multiple sclerosis include Relapsing-Remitting MS (RRMS), Primary Progressive MS (PPMS), and Secondary Progressive MS (SPMS). Each form is distinguished by differences in rates of disease development, symptoms, frequency of relapses, and treatment options. Before these stages, some individuals experience what is known as a Clinically Isolated Syndrome (CIS), where they show early signs of suggestive MS, suggesting early presence of MS, but do not fully meet the full diagnostic criteria. 

RRMS, considered to be the most prevalent form, is denoted by specific relapses with recurrence of heightened symptoms. Over time, many clients with RRMS gradually transition to SPMS,  during which symptoms progressively intensifies, neurological function continues to decline, though occasional relapses may still occur. In contrast, PPMS is marked by a steady and continuous worsening of symptoms from the onset, without distinct relapses or remissions. This subtype however, is less common, affecting approximately 10% of patients diagnosed with MS.  

Depression is a serious mental health condition that can affect anyone, regardless of age, background, and status. Although its exact cause remains widely unknown, many research suggests that it arises from a combination of factors, including genetics, environmental stress, and even as specific as the composition of one’s gut microbiome, which has been linked to mood regulation through the gut-brain axis. 

This mood disorder is characterized by persistent feelings of sadness, loss of interest or pleasure, and hopelessness. It affects neurological activity such as concentration, sleep, appetite, and overall energy levels. Beyond emotional symptoms, depression can also have significant impacts physically, contributing to fatigue, aches, or digestive problems. Because of its wide-ranging effects, depression is not simply a temporary state or low mood, rather a serious chronic condition that requires understanding with often professional treatment to manage effectively.  

To explore how Multiple Sclerosis initiated changes in the gut microbiome, (source) analyzed the differences in gut bacteria populations in fecal samples of household healthy controls, and individuals with different MS types associating with severity score (MSSS), while considering treatment status. 16S RNA was used to study the global microbial alpha and beta diversity of samples, using the V4 region. The 576 original pairs were processed and sequenced in 2 cohorts, and 500 processed pairs were used for the final diversity analysis. Overall, (source) noted an increase in Akkermansia muciniphila, Ruthenibacterium lactatiformans, Hungatella hathewayi and Eisenbergiella tayi populations in patients with MS. Also, they noticed a decrease in Faecalibacterium prausnitzii and Blautia species and changes in metabolism for MS patients. 

Despite these findings, research on the association of depression effects on the gut microbiome along with MS effects have been limited. (source) identified key microbial differences in patients with MS along with metabolic effects, (source) also noted that depression decreased gut microbiome diversity overall, however the connection between all three aspects, the depression and MS on the gut microbiome, is not clearly understood. Further research into the effects of both depression and MS on the gut microbiome open doors to study the intricacies of the gut-brain-axis, which could provide better insight into the relationship between the gut microbiome not only with physical health, but mental health. 

To study this connection further, we hope to build on findings by (source). Using the 16S rRNA sequencing from (source) we hope to investigate microbial changes in patients with different MSSS scores, while also considering the additional factor of depression presence. Our study will aim to analyze gut microbial diversity differences in a total of six controls and experimental groups and compare diversity scores, assessing the effects of MS and depression. We also hope to determine specific bacterial species which act as indicators for groups, furthermore assessing the function of these species with the goal of linking them to treatment options. 



Hypothesis and prediction 

How does the presence of depression and the severity of Multiple Sclerosis impact the gut microbial diversity and composition in patients? 

This study aims to explore how and if the presence of depression and the severity of Multiple Sclerosis affect the gut microbiome composition and diversity. We know from previous studies that the effect of depression will cause the diversity of the gut microbiome to decrease. We also know that changes in the gut microbiome due to MS occur, with less severe cases causing a decrease in diversity yet more severe cases causing an increase. We hypothesize the impact of depression and MS on patients that have both will cause distinct changes in the gut microbiome; RRMS patients with depression will have a significantly decreased gut microbiome diversity while PMS patients with depression will retain diversity similar to the control. 

In the past, it has been determined that the presence of depression can affect the composition of the microbiome. In a study performed by Li et al., the fecal matter of patients with or without depression were analyzed and sequenced. The researchers compared the 16S RNA gene found in bacteria and observed that there was a significant decrease in alpha diversity when comparing patients with depression to patients without depression. Though the exact mechanism is not known, they found that the abundance of certain major species of bacteria in the gut were significantly reduced which suggests that the presence of depression somehow alters the microbiome, reducing diversity. These findings support the hypothesis that in patients with both MS and depression, depression will contribute to a decrease in microbiome diversity. 

The relationship between the severity of MS and diversity within the gut microbiome is not well known, but there are differences in multiple sclerosis severity scores between different types of MS. Previous studies have identified that certain types of MS are more likely to reduce the diversity of the gut microbiome while others are more likely to increase diversity. Gupta et al., performed a study where they collected fecal samples of MS patients and found that in RRMS, there was a significant decrease in alpha diversity and a significant difference in beta diversity. In a study on PPMS and the gut microbiome by Kozhieva et al., the researchers found that the alpha diversity in participants with PPMS was significantly higher than participants without PPMS. This supports our hypothesis that in patients with MS and depression, those with RRMS and depression will have significantly less diverse gut microbiomes than the controls, however those with PMS and depression may have similar diversity values to controls as PMS increases diversity while depression decreases it. 




CODE PROCESSING

demux_seqs.qzv
table.qzv
AFTER DEMULTIPLEXING (before denoising):
Data/information needed
Your answer
Total number of reads
15,206,072 reads
Total number of samples
924 samples
Range of sequencing depth
(i.e. min to max)
36911
Maximum read length (in bp)
151 bp
Were all the reads the same length?
No
Truncation length selected
(format ‘left-right’, ex. ’25-350’)
1-151
 


Median Phred score cutoff: 35
Truncation length: 1-151
AFTER DENOISING AND CLUSTERING:
Data/information needed
Deblur
Total number of reads retained
112523
Total number of ASVs
185
Total number of samples
48
Range of sequencing depth
(i.e. min to max)
2923


Experimental Aims and Rationale
Aim 1: To determine if the type of MS and presence of depression together have an effect on the gut microbiome.

Based on previous studies mentioned above, MS severity and depression have different effects on the microbiome diversity and composition. According to (source), RRMS increases diversity of the gut microbiome while PMS reduces diversity. On the other hand, (source) states that, presence of depression decreases diversity of the gut microbiome. Neither study investigated the effect of both depression and MS severity on the diversity of the gut microbiome. By analyzing the gut microbial diversity differences in control and experimental groups, including those who have depression alone, RRMS or PMS alone, or both, this study will provide some insight on this topic. 

To achieve this, we will process our data through qiime first, eliminating problematic reads. We will then transfer our processed data to R using read.tsv and read.delim, where we will make our phyloseq object using Phyloseq R. We will organize our data into the following 6 groups: No Depression No MS, No Depression RRMS, No Depression PMS, Depression No MS, Depression RRMS and Depression PMS. Next, we will run our diversity analyses. First, we will measure alpha diversity of all groups with a focus on Faith’s Phylogenetic Diversity as it takes richness, evenness and phylogenetic distance into account. We will use the Pictane package in R to complete this analysis. Our goal of determining alpha diversity is to establish microbial diversity within all the groups. Second, we will perform beta diversity analysis using weighted UniFrac to examine significant differences later on in analysis between groups using the R Phyloseq package. Weighted UniFrac will be used due to its ability to measure abundance. After completing our diversity analyses, we will compare groups to determine if there are any significant differences in alpha and beta diversity values. First we will run a shapiro test to confirm all our groups are non-parametric. Assuming they are non-parametric, we will use kruskal-wallis and PERMANOVA tests to determine significance using built in R packages. We will combine these results with the results from our diversity analysis and display them on a plot using ggplot2. These analyses will provide crucial information regarding diversity differences between groups, and will determine how the presence of depression and varying MS types affect the gut microbiome. 


Aim 2: To determine the prevalence of major bacterial species under different conditions (MS or not, depression or not etc.)

Depending on the type of MS a person has, the major bacteria comprising the gut microbiome can differ significantly as some bacteria thrive under the environmental conditions provided by different types of MS. Depression has also been found at specific levels to cause certain bacterial species to become more prominent. While the effects of each condition on prevalence of major bacterial species have been studied independently, the effects of the conditions combined have not been well researched. We hope to determine if specific bacterial species will become more prevalent under the presence of both conditions depending on the type of MS and the presence of depression.

We processed our data through qiime to determine which reads should be removed. We then produce a taxonomy.qza to determine the bacterial species present under each sample. Under R we will take the samples and group them to determine which bacterial species are most prominent under the same conditions. We will then perform a test to see if the difference is significant between conditions. (depression and RRMS, depression and PMS etc conditions, no depression PMS, no depression RMS, control without depression, control with depression).



Aim 3: Determine the underlying biological mechanisms causing major bacterial species to become more or less prominent.
Aim 3: To examine how the gut microbiome function changes with depression and Multiple Sclerosis severity.
After identifying differences in microbial diversity in Aim 1 and major bacterial species in Aim 2, our next goal is to examine how these microbial changes translate into functional differences in the gut microbiome. Understanding the predicted functional capacity of the microbiota can reveal how specific metabolic pathways may influence the progression or severity of MS and the presence of depression.

To explore these potential functional shifts, we will use PICRUSt2 to predict metagenomic functions from 16S and rRNA data obtained in earlier aims. The analysis will allow us to identify metabolic pathways that are enriched or depleted across our defined groups (No depression No MS, No Depression RRMS, No Depression PMS, Depression No MS, Depression RRMS, and Depression PMS). Functional predictions will be analysed in R, and pathway abundance differences between groups will be assessed statistically to determine significance. 

Finally, we will perform a literature comparison of the most significantly altered pathways to determine if they have known associations with immune modulation, neuroinflammation, or mood regulation. This aim will help establish potential mechanistic links between microbial functions, MS severity, and depression, providing a broader understanding of how the gut microbiome may influence neuroimmune health. 



Proposed Approach


Aim Specific Approach
Aim 1: To determine if the type of MS and presence of depression together have an effect on the gut microbiome.


Aim 2: To determine the prevalence of major bacterial species under different conditions (MS or not, depression or not etc.)


Aim 3: Determine the underlying biological mechanisms causing major bacterial species to become more or less prominent.
(MAYBE)
In QIIME2, demultiplex, denoise, and trim the reads under a median PHRED score of 30.
In QIIME2, demultiplex, denoise, clustering, and trim the reads under a median PHRED score of 30. Produce a taxonomy.qzv and taxonomy.qza file to analyze bacterial species present. 
In QIIME2, use required qza files from Aim 1 and 2 as inputs for functional prediction.
Within R, install phyloseq, vegan, ggplot2, microbiome, tidyverse, and Pictane. 


Within R, install phyloseq, vegan, ggplot2, microbiome, tidyverse, and Pictane. 


Run PICRUSt2 on feature table to predict gene families and metabolic pathways based on 16S rRNA gene sequences and export results as .tsv 
Transfer our processed data to R studio using the read functions and create an alpha rarefaction plot.
Convert the taxonomy.qza file to a taxonomy.tsv file and import into R. Create an alpha rarefaction plot




Load necessary libraries, tidyverse, phyloseq, and microbiome.
Import predicted functional tables into R using read.delim
Create a phyloseq object using Phyloseq.
Create a phyloseq object.
Use group_by and filter() to subset data into 6 groups
Subset the phyloseq object into the desired groups using group_by() and filter().
Subset the phyloseq data using group_by based on the type of MS and presence of depression into a new object and determine which bacteria are most prevalent in each condition.


Compare pathway abundances using PERMANOVA (confirmed by shapiro.test()
Using the subsetted phyloseq object, perform alpha diversity analysis using Faith's Phylogenetic Distance based on the different groups.   
Perform a shapiro.test() to determine if the data is parametric or not.


Use ggplot2 to create appropriate bar plots and heatmaps showing functional pathway differences across groups, highlighting pathways that differ significantly between depression and MSSS
Using the subsetted phyloseq object, perform the beta diversity analysis using weighted UniFrac. 
Perform the appropriate statistical test to determine whether or not the differences in groups are significant or not.
Interpret and compare with literature
After gathering alpha and beta diversity metrics, use shapiro.test() to confirm the data is non-parametric, then run Kruskal-Wallis and Permanova tests to determine any significant differences between groups. 




Finally, create a plot with the metrics and data using ggplot2 to visualize any differences in diversity. 



Participation report

Introduction: Raavin, Amy, Gerard
Hypothesis/Prediction: Raavin, Gerard
Experimental Aims: Raavin, Gerard
Approach: Raavin, Gerard
Gantt Chart: Amy
Dataset Overview: Emilia
QIIME-2: Emilia
References: Raavin, Amy, Gerard, Emilia

Everyone contributed equally to this proposal, with tasks distributed based on skills, interest and past knowledge. 












