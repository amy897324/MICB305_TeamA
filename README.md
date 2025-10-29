# MICB305_TeamA
## Oct 1
Does the composition of a patient's microbiome and prevalence of depression in a patient impact their MS severity? 
New Business
Team organization:
Weekly rotation of note takers/meeting leaders
All read.me files and scripts must be uploaded to shared GitHub repository MICB305_TeamA

Examine UJEMI database for suitable papers:
Sweet spot of specific areas in the metadata that have yet to be explored with some evidence supporting hypothesis.
Explore multiple metadata sets to find variables

Literature review:
Upstream vs. downstream hypothesis
Indirect observations

To-do before next week
Search metadata and form a short list of datasets of interest

Ideas for MS metadata
The Microbiome composition differences in patients with/without varying types of depression(Gut brain axis) 

Does the composition of a patient's microbiome and prevalence of depression in a patient impact their MS severity? 

https://pmc.ncbi.nlm.nih.gov/articles/PMC3181849/ (ask prof)
https://pubmed.ncbi.nlm.nih.gov/35508109/
https://psychiatryonline.org/doi/10.1176/jnp.23.3.jnp261
https://pmc.ncbi.nlm.nih.gov/articles/PMC10146621/
https://pubmed.ncbi.nlm.nih.gov/36113426/
https://pubmed.ncbi.nlm.nih.gov/30310254/
https://www.thelancet.com/journals/ebiom/article/PIIS2352-3964(23)00092-0/fulltext


How does the microbiome of patients as well as the different allergies they have impact the prevalence and severity of MS? 

## Oct 8
With MS dataset, only problem is not many patients with clinical depression (can still use, sufficient)
Can random sample due to disproportionate amount of people with not
Divide by 2 because 2 samples for each person
Post-partum depression = different mechanism 
Use as confounding variable 
Duplicate data = 2 swabs taken
Filtering beforehand
Remove duplicates
Will still take a while
So plan ahead
Have someone import it beforehand
Do it in beginning of week to avoid slow
To only obtain necessary variables
Will take too long if too big
After filtering, process what’s left
All processing in QIIME2
Clean metadata to wanted variables 
Summarize
Controls
Ask Bessie next week about it
Look at severity of MS for those individuals 
MSSS
Data analysis in R
Good specific question
Good correlation of gut-brain axis, depression, and MS
Keep them updated of how long processing takes
Update agenda and meeting notes on Github
Proposal due on oct 26
Have some of it analysed 


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

Other scientific articles.

https://pmc.ncbi.nlm.nih.gov/articles/PMC9355758/ (DEPRESSION ON DIVERSITY)

In the past, it has been determined that the presence of depression can affect the composition of the microbiome. In a study performed by Li et al., the fecal matter of patients with or without depression were analyzed and sequenced. The researchers compared the 16S RNA gene found in bacteria and observed that there was a significant decrease in alpha diversity when comparing patients with depression to patients without depression. Though the exact mechanism is not known, they found that the abundance of certain major species of bacteria in the gut were significantly reduced which suggests that the presence of depression somehow alters the microbiome.

https://www.neurology.org/doi/10.1212/NXI.0000000000200355 (MS on gut diversity)
https://pmc.ncbi.nlm.nih.gov/articles/PMC10001679/ (got the third link from here)
https://bmcmicrobiol.biomedcentral.com/articles/10.1186/s12866-019-1685-2 (PPMS alpha increase)

The relationship between the severity of MS and diversity within the gut microbiome is not well known, but there are differences in multiple sclerosis severity scores between different types of MS. Previous studies have identified that certain types of MS are more likely to reduce the diversity of the gut microbiome while others are more likely to increase diversity. Gupta et al., performed a study where they collected fecal samples of MS patients and found that in RRMS, there was a significant decrease in alpha diversity and a significant difference in beta diversity. In a study on PPMS and the gut microbiome by Kozhieva et al., the researchers found that the alpha diversity in participants with PPMS was significantly higher than participants without PPMS.


Article Depression Different Bacteria

Article says at the species level there was a significant difference depression had highest of Coprococcus catus while this bacteria was significantly reduced Bacteroides barnesiae
https://pmc.ncbi.nlm.nih.gov/articles/PMC9355758/

## October 29
### Introduction
Multiple sclerosis (MS) is a chronic autoimmune disorder in which the immune system destroys myelin cells. MS manifests in several subtypes, including Relapsing-Remitting MS (RRMS), characterized by episodic relapses and remissions, and Progressive MS (PMS), involving gradual worsening from onset. Depression is a serious mental health disorder, often associated with MS(source), marked by persistent sadness, hopelessness, and cognitive and physical disturbances. Studies have also suggested the gut microbiome, the diverse community of microorganisms in the digestive tract, is deeply connected to both depression and MS, also introducing interesting implications on the gut-brain axis, defined as a bidirectional route connecting the gut microbiome to the brain.

The connection between depression and MS, depression and the gut microbiome and MS and the gut microbiome while considering the gut-brain axis has been researched in the past. Minden et al. (1987) found that depression is significantly more common in MS patients, supporting the idea of a link between MS and depression. Chen, et al., (2022) also states that the composition of the gut microbiome has been found to be different in individuals with depression compared to without depression. Maciak et al. (2022) propose that dysregulation of the gut-brain axis may drive neuroinflammation via activation of the NLRP3 inflammasome, thereby suggesting links between gut and neural dysfunction with autoimmunity in MS.

To explore how Multiple Sclerosis initiated changes in the gut microbiome, (source) used 16S RNA to study the global microbial alpha and beta diversity of samples, using the V4 region. Overall, (source) noted an increase in Akkermansia muciniphila, Ruthenibacterium lactatiformans, Hungatella hathewayi and Eisenbergiella tayi populations in patients with MS. Also, they noticed a decrease in Faecalibacterium prausnitzii and Blautia species and changes in metabolism for MS patients. Furthermore, (source) indicated there were significant differences in beta diversity scores. These results indicate significant changes in gut microbial diversity due to MS, and more suggest research in this area would be valuable.

Overall, the results of past studies indicate that MS and depression separately have effects on the gut microbiome, as well as a connection to the gut-brain axis. Though extensive research has been done on the relationships between MS and depression, depression and the gut microbiome, and the gut microbiome and MS, research into the effect of both depression and MS severity on microbiome diversity has been limited.

To study this connection further, we hope to build on findings by (source). Our study will aim to analyze gut microbial diversity differences in a total of six controls and experimental groups and compare diversity scores, assessing the effects of MS severity and depression alone on the gut microbiome diversity and composition, but also the effect both have together. We also hope to determine bacterial species specific to each group, with the goal of finding functional differences between microbial communities. Ideally, this study will help bridge the gap between depression, MS severity and the gut microbiome, and provide some insight into the effect of both physical and mental health on the gut microbiome and furthermore the gut-brain axis.

Hypothesis and prediction
How does the presence of depression and the severity of Multiple Sclerosis impact the gut microbial diversity and composition in patients? 

This study aims to explore how and if the presence of depression and the severity of Multiple Sclerosis affect the gut microbiome composition and diversity. We know from previous studies that the effect of depression will cause the diversity of the gut microbiome to decrease. We also know that changes in the gut microbiome due to MS occur, with less severe cases causing a decrease in diversity yet more severe cases causing an increase in diversity. We hypothesize the impact of depression and MS on patients that have both will cause distinct changes in the gut microbiome; RRMS patients with depression will have a significantly decreased gut microbiome diversity while PMS patients with depression will retain diversity similar to the control. Additionally, we hypothesize that there will be different bacterial species in each of our six control and experimental groups due to the effects depression and MS severity have on microbiome composition. 

In the past, it has been determined that the presence of depression can affect the composition of the microbiome. In a study performed by Li et al., the fecal matter of patients with or without depression were analyzed and sequenced. They found that the abundance of certain major species of bacteria in the gut were significantly reduced which suggests that the presence of depression somehow alters the microbiome, reducing diversity. Liu, et al., (2022) found that major depressive disorder led to a significant difference in beta diversity in the composition of beneficial bacteria compared to individuals without depression. Additionally, (source) says at the species level, there was a significant difference in microbial composition of people with depression, with Coprococcus catus being increased and Bacteroides barnesiae being reduced. These findings support the hypothesis that depression will contribute to a decrease in microbiome diversity, and may indicate that in patients with both MS and depression, depression will contribute to a less diverse gut microbiome. Also, these findings indicate that the composition of the gut microbiome will be altered due to depression, suggesting that in patients with MS and depression, depression may contribute to a change in gut microbiome composition. 

Previous studies have identified that certain types of MS are more likely to reduce the diversity of the gut microbiome while others are more likely to increase diversity. Gupta et al., performed a study where they collected fecal samples of MS patients and found that in RRMS, there was a significant decrease in alpha diversity and a significant difference in beta diversity. In a study on PPMS and the gut microbiome by Kozhieva et al., the researchers found that the alpha diversity in participants with PPMS was significantly higher than participants without PPMS. Additionally, Chen et al. (2016) found that patients with MS display a distinct gut-microbiota composition compared to healthy controls, with higher abundances of genera such as Pseudomonas, Mycoplana, Blautia and Dorea, and lower abundances of Parabacteroides, Adlercreutzia, and Prevotella. This supports our hypothesis that patients with RRMS will have significantly less diverse gut microbiomes than the controls, and it is possible that the added aspect of depression in patients with both may decrease diversity further. However those with PMS and depression may have similar diversity values to controls as PMS increases diversity while depression decreases it. Because MS also causes changes in microbiome composition, indicating patients with both depression and MS may have significant gut microbiome changes as both depression and MS alter the expression of certain species, providing support for our hypothesis that gut microbiome composition will be different in each group.

### Experimental Aims and Rationale
#### Aim 1: To determine if the severity of MS and presence of depression together have an effect on the gut microbiome.
Based on previous studies mentioned above, MS severity and depression have different effects on the microbiome diversity and composition. According to (source), RRMS increases diversity of the gut microbiome while PMS reduces diversity. On the other hand, (source) states that, presence of depression decreases diversity of the gut microbiome. Neither study investigated the effect of both depression and MS severity on the diversity of the gut microbiome. By analyzing the gut microbial diversity differences in control and experimental groups, including those who have depression alone, RRMS or PMS alone, or both, this study will provide some insight on this topic.

Aim 1a: processing the data to allow us to perform further down diversity analysis:

We will process our data through qiime first, eliminating problematic reads. We will then transfer our processed data to R using read.tsv and read.delim, where we will make our phyloseq object using Phyloseq R. We will organize our data into the following 6 groups: No Depression No MS, No Depression RRMS, No Depression PMS, Depression No MS, Depression RRMS and Depression PMS.

Aim 1b: Calculating alpha diversity values to find the overall diversity of each of our 6 groups: 

First, we will measure alpha diversity of all groups with a focus on Faith’s Phylogenetic Diversity as it takes richness, evenness and phylogenetic distance into account. We will use the Pictane package in R to complete this analysis. Our goal of determining alpha diversity is to establish microbial diversity within each of the groups. This can be used during further analysis to determine which groups are more diverse than others overall. 

Aim 1c: Calculating beta diversity values to find how different the groups are from one another:

Second, we will perform beta diversity analysis using weighted UniFrac to examine significant differences later on in analysis between groups using the R Phyloseq package. Weighted UniFrac will be used due to its ability to measure abundance as well as phylogenetic distance. Finding beta diversity values will provide some insight into whether groups are made up of similar bacteria or very different bacteria types. 

Aim 1d: Comparing alpha and beta diversity values to determine if there is significance: 

After completing our diversity analyses, we will compare groups to determine if there are any significant differences in alpha and beta diversity values. First we will run a shapiro test to confirm all our groups are non-parametric. Assuming they are non-parametric, we will use kruskal-wallis and PERMANOVA tests to determine significance using built in R packages. We will combine these results with the results from our diversity analysis and display them on a plot using ggplot2. These analyses will provide crucial information regarding diversity differences between groups. 

Furthermore, Aim 1 will allow us to determine if MSSS and presence of depression cause significant changes in gut microbiome diversity both together and separately, providing insight into the research question. 
#### Aim 2: To determine the prevalence of major bacterial species under different conditions (MS or not, depression or not etc.)
Depending on the type of MS a person has, the major bacteria comprising the gut microbiome can differ significantly as some bacteria thrive under the environmental conditions provided by different types of MS. Depression has also been found at specific levels to cause certain bacterial species to become more prominent. While the effects of each condition on prevalence of major bacterial species have been studied independently, the effects of the conditions combined have not been well researched. We hope to determine if specific bacterial species will become more prevalent under the presence of both conditions depending on the type of MS and the presence of depression.

We processed our data through qiime to determine which reads should be removed. We then produce a taxonomy.qza to determine the bacterial species present under each sample. Under R we will take the samples and group them to determine which bacterial species are most prominent under the same conditions. We will then perform a test to see if the difference is significant between conditions (depression and RRMS, depression and PMS etc conditions, no depression PMS, no depression RMS, control without depression, control with depression).
Aim 3: To examine how the gut microbiome function changes with depression and Multiple Sclerosis severity.
After identifying differences in microbial diversity in Aim 1 and major bacterial species in Aim 2, our next goal is to examine how these microbial changes translate into functional differences in the gut microbiome. Understanding the predicted functional capacity of the microbiota can reveal how specific metabolic pathways may influence the progression or severity of MS and the presence of depression.

#### Aim 3a: Perform a functional analysis of the different microbial communities making up our groups: 

To explore these potential functional shifts in control and experiment groups, we will use PICRUSt2 to predict metagenomic functions from 16S and rRNA data obtained in earlier aims. The analysis will allow us to identify metabolic pathways that are enriched or depleted across our defined groups. Functional predictions will be analysed in R using DESeq2, and pathway abundance differences between groups will be assessed statistically. This will help us determine if any of our group's metabolic pathways and functions differ significantly from another group. This builds on our research question; it examines the effects of MSSS and depression on microbiome composition and function by providing insight into functional differences in microbial communities making up groups. 

Aim 3b: Researching most significantly altered pathways: 

Finally, we will perform a literature comparison of the most significantly altered pathways to determine if they have known associations with immune modulation, neuroinflammation, or mood regulation. This aim will help establish potential mechanistic links between microbial functions, MS severity, and depression, providing a broader understanding of how the gut microbiome may influence neuroimmune health. 

Overall, this aim will help investigate the research question further. With Aims 1 and 2, not only would we have determined significant microbial diversity differences between groups, but also specific compositional similarities and differences. Aim 3 helps add meaning to these analyses by investigating functional differences due to microbial composition and their implications towards neuroimmune health and the gut-brain axis.

### Proposed Approach
#### Data Processing
A
Import raw sequences and filter to generate demux_seqs-filtered.qza within the Qiime2 environment
B
Using Deblur, denoise and truncate the dataset to generate rep-seqs.qza, table.qza
C
Extract 16S sequences from from the Silva reference database to generate ref-seqs-trimmed.qza
D
Train classifier with ref-seqs-trimmed.qza to generate classifier.qza
E
Use the trained classifier to assign taxonomy to the reads, generateing taxonomy.qza, taxonomy.qzv, and taxa-bar-plots.qzv
F
Use rep-seqs.qza to generate a phylogenetic tree, rooted-tree.qza
G
Export the files from Qiime2
H
In R, install phyloseq, ape, tidyverse, and vegan packages, import and load R-compatible metadata.tsv, feature-table.txt, taxonomy.tsv, and tree.nwk
I
Use the existing corrected_ms_metadata.tsv to generate tidied_metadata.tsv, which includes a new column grouping SPMS and PPMS into PMS.
J
Generate a phyloseq object with tidied_metadata
K
Filter phyloseq object to remove samples with less than 200 reads, as well as mitochondrial and chloroplast genetic information
L
Generate alpha rarefaction curve using rarefy()



#### Aim Specific Approach
Aim 1: To determine if the type of MS and presence of depression together have an effect on the gut microbiome.
Aim 2: To determine the prevalence of major bacterial species under different conditions (MS or not, depression or not etc.)
Aim 3: To examine how the gut microbiome function changes with depression and Multiple Sclerosis severity.
In QIIME2, demultiplex, denoise, and trim the reads under a median PHRED score of 30.
In QIIME2, demultiplex, denoise, clustering, and trim the reads under a median PHRED score of 30. Produce a taxonomy.qzv and taxonomy.qza file to analyze bacterial species present. 
In QIIME2, use required qza files from Aim 1 and 2 as inputs for functional prediction.
Within R, install phyloseq, vegan, ggplot2, microbiome, tidyverse, and Pictane. 


Within R, install phyloseq, vegan, ggplot2, ggVennDiagram, microbiome, and tidyverse.
Run PICRUSt2 on feature table to predict gene families and metabolic pathways based on 16S rRNA gene sequences and export results as .tsv 
Transfer our processed data to R studio using the read functions and create an alpha rarefaction plot.
Convert the taxonomy.qza file to a taxonomy.tsv file and import into R. Create an alpha rarefaction plot.
Load necessary libraries, tidyverse, phyloseq, and microbiome.
Import predicted functional tables into R using read.delim
Create a phyloseq object using Phyloseq.
Create a phyloseq object.
Use group_by and filter() to subset data into 6 groups
Subset the phyloseq object into the desired groups using group_by() and filter().
Subset the phyloseq data using group_by based on the type of MS and presence of depression into a new object.
Compare pathway abundances using PERMANOVA (confirmed by shapiro.test()
Using the subsetted phyloseq object, perform alpha diversity analysis using Faith's Phylogenetic Distance based on the different groups.   
Perform core microbiome assessment to see unique and overlapping taxa in each group’s core microbiome.
Use ggplot2 to create appropriate bar plots and heatmaps showing functional pathway differences across groups, highlighting pathways that differ significantly between depression and MSSS
Using the subsetted phyloseq object, perform the beta diversity analysis using weighted UniFrac. 
Visualize core microbiome using ggVennDiagram.
Interpret and compare with literature
After gathering alpha and beta diversity metrics, use shapiro.test() to confirm the data is non-parametric, then run Kruskal-Wallis and Permanova tests to determine any significant differences between groups. 
Make references to the literature to analyze the venn diagram of core microbiome


Finally, create a plot with the metrics and data using ggplot2 to visualize any differences in diversity. 






### Weekly Timeframe


### Dataset Overview
The data used for this analysis was obtained from Gut microbiome of multiple sclerosis patients and paired household healthy controls reveal associations with disease risk and course, published in the Cell Press Journal in 2022. The data obtained includes the samples and metadata of 924 participants, which was then denoised using the Deblur tool in QIIME2.

Figure 1: PHRED score for each base before denoising.

To determine the metrics for truncating the data when denoising, we first looked at the plot of the data’s PHRED scores, as shown in Figure 1. Upon seeing that each nucleotide had a median PHRED score above thirty, which indicates high quality, we chose to keep all the base pairs. With Deblur, we truncated the data at 151 neucleotides (nts), which was the maximum length. The Deblur tool automatically excludes reads that are less than the selected nts length, which removed the few samples that had fewer than 151 nucleotides.

Data/information needed
Before Denoising
After Denoising
Total number of reads
15,206,072 reads
9,102,156
Total number of samples
924
913
Range of sequencing depth
(i.e. min to max)
1-36911
5-20269

Table 1: Sequencing depth before and after using Deblur to denoise data





### Participation report
Introduction: Raavin, Amy, Gerard
Hypothesis/Prediction: Raavin, Gerard
Experimental Aims: Raavin, Gerard, Amy
Proposed Approach: Raavin, Gerard, Amy, Emilia
Weekly Timeframe: Amy
Dataset Overview: Emilia
QIIME-2: Emilia
References: Raavin, Amy, Gerard, Emilia

Everyone contributed equally to this proposal, with tasks distributed based on skills, interest, and past knowledge. 

### References


