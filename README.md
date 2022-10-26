# Survival-Analysis-of-cancer-data

# List of used libraries in survival analysis :-
library(survminer)
library(survival)

# Read the data.
data_s=read.table("C:/Users/91973/Documents/CGGA.mRNAseq_693_clinical.20200506.txt",sep="\t",header = T,row.names = 1)
print(head(data_s))

#to estimate and interpret survival functions from the survival data.
fit = survfit(Surv(OS,Censor..alive.0..dead.1.) ~ Gender,data = data_s)

#To plot a ggplot of survival estimation of given data .
ggsurvplot(fit,data=data_s,surv.median.line = "hv",pval=T,risk.table = T)
![survival_analysis](https://user-images.githubusercontent.com/110582335/197965527-24a59f35-4117-4bc0-b909-eb015dda6e6a.png)
