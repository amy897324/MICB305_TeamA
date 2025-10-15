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

