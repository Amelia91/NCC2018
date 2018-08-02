# Higher temperatures increase suicide rates in the United States and Mexico

Replication materials for _Burke, González, Baylis, Heft-Neal, Baysan, Basu, and Hsiang (2018)_.

The materials in this repository allow users to reproduce the figures appearing in the main text of the paper.

If you find meaningful errors in the code or have questions or suggestions, please contact Marshall Burke at mburke@stanford.edu.

## Organization of repository

* **inputs**: all inputs for analysis.
* **outputs**: outputs of analysis are written to this directory.
* **outputs/raw_figures**: scripts MakeFigure1-5.R will generate pdf figures in this directory.
* **outputs/published_figures**: the versions of the figures that appear in the paper.
* **scripts**: scripts for replication of figures, tables, and calculations.
* **NCC2018_replication.Rproj**: organizes the replication materials into an RStudio Project. 


### List of data files in NCC2018/inputs/
* **BarrecaEtAlACData.rds:** A/C data from Barreca et al 2016
* **CDC_UCD_forAnalysis.rds:**
* **income/BEA_Income_1969_2014.csv:** Income data from BEA
* **income/GDP_deflator.csv:** GDP deflator data from the ST Louis Fed
* **map_boundaries/Mex_adm1.rds:** Map boundaries for Mexican states
* **map_boundaries/USA_adm1.rds:** Map boundaries for US states
* **OkoroEtAl2005_GunData.rds:** Gun violence data from Okoro et al 2005
* **OtherSuicideStudies.csv:** Effects estimated by other suicide studies
* **projections/PopulationProjections_Historical.csv** Population projections for past years
* **projections/PopulationProjections.csv** Population projections for future years
* **projections/TemperatureProjections_mex.csv** Temperature projections for Mexico
* **projections/TemperatureProjections_us.csv** Temperature projections for US
* **SuicideCountyMonth_Gender_AgeAdj_FullPeriod.rds** Suicide rates calculated by gender
* **SuicideData_Mexico.csv** Primary analysis data file for Mexico
* **SuicideData_US.csv** Primary analysis data file for US
* **twitter_data.Rds** Primary analysis data file for twitter analysis
* **US_FIPS_Codes.csv** US FIPS codes

* **bootstrap_runs/BootstrapMainModel_mex.csv:** Stored bootstrapped coefficients generated in `MakeFigure1.R'
* **bootstrap_runs/BootstrapMainModel_us.csv:** Stored bootstrapped coefficients generated in `MakeFigure1.R'
* **bootstrap_runs/BootstrapStateEffects_main_mex.csv** Stored bootstrapped coefficients generated in `MakeFigure3.R' 
* **bootstrap_runs/BootstrapStateEffects_state_mex.csv** Stored bootstrapped coefficients generated in `MakeFigure3.R'
* **bootstrap_runs/BootstrapStateEffects_main_us.csv** Stored bootstrapped coefficients generated in `MakeFigure3.R'
* **bootstrap_runs/BootstrapStateEffects_state_us.csv** Stored bootstrapped coefficients generated in `MakeFigure3.R'
* **bootstrap_runs/BootstrapProjections_mex.csv** Stored bootstrapped coefficients generated in `MakeFigure5.R'
* **bootstrap_runs/BootstrapProjections_us.csv** Stored bootstrapped coefficients generated in `MakeFigure5.R'




## Instructions
The repository is ~250Mb unzipped.

Users can manage replication through the R project "NCC2018_replication.Rproj". Alternatively users can set working directory to NCC2018 and run scripts independently.

MakeFigure1 - MakeFigure 5 generate each of the figures in the main text along with relevant calculations cited in the text.

The figures produced by these scripts will be slightly visually different than the published figures because post-processing was done in Adobe Illustrator. Published versions of the figures are available in the published_figures directory.

The runtimes of the scripts are:
* MakeFigure1.R: 1 minute (45 minutes if run commented out bootstrapping code)
* MakeFigure2.R: 1 minute
* MakeFigure3.R: 2 minutes (>1 hour if run commented out bootstrapping code)
* MakeFigure4.R: 4 minutes
* MakeFigure5.R: 30 seconds (45 minutes if run commented out bootstrapping code)

functions.R: loads packages and defines functions used in the MakeFigure scripts.
MakeFigure2.R must be run before MakeFigure5.R because it generates an input to Figure 5.


## R packages required
* **classInt**
* **data.table**
* **dplyr**
* **lfe**
* **multcomp**
* **plotrix**
* **RColorBrewer**
* **readr**
* **reshape2**
* **sampling**
* **sp**
* **splines**

Scripts were written in R 3.5.0.

Users can run the following command to install the most recent versions of these packages:

```R
install.packages(c('classInt', 'data.table', 'dplyr', 'lfe', 'multcomp', 'plotrix', 'RColorBrewer', 'readr', 'reshape2', 'sampling', 'sp', 'splines'), dependencies = T)
``` 
