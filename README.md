# MICB305_TeamA

# Dec 3

## Agenda
- see if functional analysis should be included
- ask about manuscript structure
- any new updates on presentation slides
- final thoughts

## Meeting Notes

# Nov 26

## Agenda
- go over presentation slides
- potentially look over aims further
- questions about oral presentation

## Meeting Notes
Presentation
   - Change title after finding last conclusions
   - Define what “MS” means first
        - Same for RRMS and PMS
   - Good amount of graphics and text
   - “Why is this important”
        - Good to include
        - Can be a single point on previous slide
   - Use more informative visuals
   - Start with dataset slide before breakdown of 6 groups
   - Don’t need a figure for every slide
        - Can be a continuation of previous ones
   - No need to talk about conclusions right away
        - Basically the title of the study
        - Put alpha and beta together
        - Ok to keep
   - “Alpha diversity analysis revealed…”
        - Revise to a more concise title
        - Remove the points, just show plot
            - Already shown as y-axis
            - Don’t include legend
        - Dont show shannon and simpson and pick one of chao or observed 
            - And do brief summary (“it shows it was reduced…”)
            - Make graph wider for remaining 2
        - Make boxplots the same color for RRMS/PMS
   - But for manuscript show all 4 figures
   - “Beta diversity analysis revealed…”
        - Not every comparison is relevant
        - Figure 2 on manuscript panel a and b
   - Core microbiome
        - Figure 3 do two panels
   - Omit indicator species
        - Don’t include on manuscript
        - Filter for pms, then depression and not
   - “In ancom-bc2 analysis…”
        - Get rid of slide
        - Filter so just run with depression and not
   - For functional analysis
        - Filter for only PMS and compare between depression and no depression
        - Send abs file path of input
        - Email if needed
   - Presentation slides
        - Raavin = alpha and beta
        - Emilia = conclusion
        - Gerard = core microbiome
        - Amy = Intro

# Nov 19

## Agenda
- go over aims analysis for all 3.
- possibly go over fixed revisions.

## Meeting Notes
Aim 1
For beta: Weight, unweighted, and 
Alpha: do shannon as well, and observed 
Dunn test

Aim 2 
This graph with only PMS, control, control_depression, pms_depression 
RMS as separate graph
Only 4 at a time
For ANCOM pairwise comparison should be between PMS-depression and PMS–no depression

Github
Agenda and meeting notes

Presentation 
10mins present project
Just need data
Make draft powerpoint of what you have so far by next meeting
Then will be ready to write up manuscript
Upload all scripts and figures to github

# Nov 12

## Agenda
- Get revisal feedback from Avril and Bessie
- go over next steps and what to get done by next week and future with our project

## Meeting Notes
Proposal revision
- Title is too confirmed as if we’ve accomplished the research already
   - Moreso for final manuscript
   - Don’t use “modulate”
   - Investigating the effect of…
- Language is not “scientific” enough
   - Avoid using words like “interesting”, etc
   - Expand on what exactly other papers found rather than stating “there was a difference”
- Focus revision based on what TA said and changing those for what’s due on sunday
- Hypothesis
   - If we want to keep the claims in our hypothesis, we have to explain our perspective of it
        - Explained in further sections so change order of paragraphs
- Aims
   - Misinformation about what functional analysis reveals
        - As well as how to approach aim 3 overall
        - Broad statements/claims
        - Does it tell you pathway abundance?
   - Explain more on why we chose diversity metrics and what it reveals for us
- Overall add more descriptions
- cause and effect
- fix references
  

# Nov 5

## Agenda
- Ask questions about next steps
- presentation
- Assignment 6

## Meeting Notes
By next meeting, complete some analysis done for some aims
 By Oct 19, have most aims analysed
Go over presentation slides by Oct 29
Not everything has to necessarily be done by presentation


# Oct 29

## Agenda
- get more feedback on proposal draft

## Meeting Notes
Final proposal review
Cite more
Reorganize intro
https://docs.google.com/document/d/1dazcS31jXVaTHwVo_dbG_dvDyYjQysJTgvbyOvpcPVw/edit?tab=t.iove6sknk98q#heading=h.4q66811raij

# Oct 22

## Agenda
- Go through proposal
- get lots of feedback
- make sure RQ is good
- check analysis

## Meeting Notes
Add first 3 meeting notes onto github
Move proposal to a different file on github

Title: don't sound conclusive or too broad, can start with an ING verb. 
introduction and background: purpose is to say what we know and what we are trying to find. Avoid explaining too much about MS and depression itself, give a brief overview. 
Look for some things a bit broader for introduction.
What we want to write about is more about gut microbiome
Targeting our actual research question
Link depression with gut microbiome
Link MS with gut microbiome
In rubric, not much need to describe the dataset we’re going to be using
At max, only 1 paragraph
Start with significance from beginning
Find many studies supporting points for introductions, depression and MS = bad, how is affecting gut microbiome based on what studies? 
Expand more on gap
What’s unknown

# Oct 15

## Agenda
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

## Meeting Notes
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

# Oct 8

## Agenda
- Search metadata and form a short list of datasets of interest
- Talk about our potential RQ
- think thoroughly about hypothesis
- what types of analysis would work best for our question

## Meeting Notes
- With MS dataset, only problem is not many patients with clinical depression (can still use, sufficient)
      - Can random sample due to disproportionate amount of people with not
      - Divide by 2 because 2 samples for each person
- Post-partum depression = different mechanism 
      - Use as confounding variable 
- Duplicate data = 2 swabs taken
- Filtering beforehand
- Remove duplicates
- Will still take a while
- So plan ahead
- Have someone import it beforehand
- Do it in beginning of week to avoid slow
- To only obtain necessary variables
- Will take too long if too big
- After filtering, process what’s left
- All processing in QIIME2
- Clean metadata to wanted variables 
- Summarize
- Controls
- Ask Bessie next week about it
- Look at severity of MS for those individuals 
- Data analysis in R
- Good specific question
- Good correlation of gut-brain axis, depression, and MS
- Keep them updated of how long processing takes
- Update agenda and meeting notes on Github
- Proposal due on oct 26
- Have some of it analysed 


# Oct 1

## Agenda
- Look at datasets
- pick which peaks interest
- think of sample RQ

## Meeting Notes
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

References


