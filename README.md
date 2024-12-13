# Rotation1

### **ECOL 596W Final Project: Data and code for Rotation 1 (Fall 2024)**

**Research Question**: Do maternal microbiota mediate plasticity of reproductive phenotypes?

**Hypothesis**: Maternal microbiota mediates anticipatory plasticity of reproductive phenotypes through microbial contributions to maternal energetics, indicative of maternal quality.

**Predictions**: Greater microbial diversity will predict the more advantageous reproductive phenotypes across mast and non-mast years. Before breeding, greater microbial diversity will predict earlier birth dates and larger litters. During lactation, which is energetically expensive, I predict that greater microbial diversity will predict faster growth rates and greater juvenile survival.

**Study System**: Wild red squirrels (*Tamiasciurus hudsonicus*) in the southwestern Yukon, Canada, who experience extreme fluctuations in food availability, since their primary food source (white spruce cones, *Picea glauca*) exhibits a "swamp and starve" reproductive strategy (masting: an overabundance of cones is produced one year, followed by three to seven years of little to no cones).

**Data**: Longitudinal data and fecal samples used in this analysis were collected from wild female red squirrels from 2008 to 2017. Each squirrel was assigned a unique identification number (squirrel_id) with a metal ear band and each reproductive attempt (litter_id) was assigned a unique number. Data on reproductive status (rep_status), birth date of litter (bdate), litter size at birth (litter_size), average growth rate of pups (avg_growth_litter), overwinter juvenile survival (juv_survived), and days since birth (days_since_part) were extrapolated and calculated using observational and morphometric data collected during live trapping and nest entry. Fecal samples were matched with each squirrels' reproductive phenotype data using squirrel_id and litter_id. Fecal samples were collected opportunistically during live trapping and DNA was extracted at a later time. The V4 region of the 16S rRNA gene was amplified and sequenced. Sequences were processed in Qiime2 and then imported into R to create a phyloseq object, which was used to calculate alpha diversity (Shannon Index, tukey transformed: ShannonT)

**Modeling**: To test whether microbial alpha diversity predicted reproductive phenotypes, and whether this relationship differed across reproductive states and non-mast/mast years, we used a linear mixed model (lme4) with a three-way interaction of ShannonT \* rep_status \* mast.x and included biologically relevant covariates and random effects of squirrel_id.x and year.

**Plotting**: Model predictions were extracted and added as a new column in the dataset. Alpha diversity was plotted against reproductive phenotype in ggplot2, faceted by reproductive status and non-mast/mast year. Pedicted values were represented by trend lines with confidence intervals and raw data points were made transparent to highlight model predictions.
