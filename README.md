# Survival-Analysis-of-cancer-data

# List of used libraries in survival analysis :-
library(survminer)
library(survival)

# Read the data.
data_s=read.table("C:/Users/91973/Documents/CGGA.mRNAseq_693_clinical.20200506.txt",sep="\t",header = T,row.names = 1)
data_s[,4]=str_replace_all(data_s[,4]," ","")
unique(data_s[,4])
print(head(data_s))

# To estimate and interpret survival functions from the survival data.
fit = survfit(Surv(OS,Censor..alive.0..dead.1.) ~ Gender,data = data_s)

# To plot a ggplot of survival estimation of given data .
ggsurvplot(fit,data=data_s,surv.median.line = "hv",pval=T,risk.table = T)
![image](https://user-images.githubusercontent.com/110582335/198823299-ba988b73-84d3-4fed-915a-9ce61902561f.png)

