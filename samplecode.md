---
title: "Analysis of Terror in the World"
author: "Aylin Kosar"
toc: true
output: html_document
---

## Upload Data

```{r message=FALSE, warning=FALSE}
setwd("~/R Data Files")
gt = read.csv("globalterrorism.csv", na.strings = "")
gt
```

## Look for Missing Values 

There are many variables and many columns that are not really needed for the analysis.

```{r}
summary(gt)
```

## Preprocess Data

Below many of the columns that are not needed are removed and result with 36 variables. Some of the variables were not factored in properly so they had to be properly factored. In order to make sure the numeric variables were factored in correctly as type numeric, the function as.numeric was used.

```{r}
cols = c('related','addnotes','scite1','scite2','scite3','ransomnote', 'summary','location', 'doubtterr', 'alternative', 'alternative_txt', 'propcomment', 'dbsource','motive','specificity','vicinity','approxdate','extended','resolution','crit1','crit2', 'crit3','multiple', 'related', 'attacktype2','attacktype2_txt','attacktype3','attacktype3_txt','success','weapsubtype1','weapsubtype1_txt','weaptype2','weaptype2_txt','weapsubtype2','weapsubtype2_txt','weaptype3','weaptype3_txt','weapsubtype3','weapsubtype3_txt','weaptype4','weaptype4_txt','weapsubtype4','weapsubtype4_txt','weapdetail','corp1','targtype2','targtype2_txt','targsubtype2','targsubtype2_txt','corp2','target2','natlty2','natlty2_txt','targtype3','targtype3_txt','corp3','target3','natlty3','natlty3_txt','gname2','gsubname2','gname3','gsubname3','guncertain1','guncertain2','guncertain3','compclaim','claim2','claimmode2','claim3','claimmode3','property','propextent', 'propextent_txt','propvalue','ishostkid','nhours','ndays','divert','kidhijcountry','ransom','ransomamtus','ransompaidus','ransomnote','hostkidoutcome','hostkidoutcome_txt','nreleased','INT_LOG','INT_IDEO','INT_MISC','INT_ANY','nhostkid','nhostkidus','ransomamt', 'ransompaid','claimmode2_txt','claimmode3_txt','targsubtype3','targsubtype3_txt')
 gt = gt[, !colnames(gt)%in% cols] 
gt$ targsubtype1_txt = factor(gt$ targsubtype1_txt, levels = c("Unnamed Civilian/Unspecified", "Police Security Forces/Officers", 
"Government Personnel (excluding police, military)", "Military Personnel (soldiers, troops, officers, forces)", "Military Unit/Patrol/Convoy", "Non-State Militia", "Laborer (General)/Occupation Identified", "House/Apartment/Residence", "Other"), ordered = TRUE)
levels(gt$targsubtype1_txt) 
gt$targtype1_txt = factor(gt$targtype1_txt) 
levels(gt$targtype1_txt) = c("Private Citizens & Property", "Military", "Police", "Government (General)", "Business", "Transportation", "Abortion Related", "Airports & Aircraft","Government(Diplomatic)", "Educational Institution", "Food & Water Supply", "Journalists & Media", "Maritime", "NGO", "Religious Figures/Institutions", "Telecommunication", "Terrorists/Non-State Militia", "Tourists", "Transportation", 
"Utilities", "Violent Political Parties", "Unknown", "Other")
gt$gsubname = factor(gt$gsubname, levels = c("Militants", "People's Liberation Forces (FPL)", "Rebels", "Separatists", "Jamaat-ul-Ahrar", "The Family",  "al-Quds Brigades",  "Intifadat Ahrar al-Iraq",  "Forces for the Defense of Democracy (FDD)", "Jaysh al-Nukhba; Al-Izzah",  "Al-Rahman Corps", "Ezzedine al-Qassam Brigades", "Ahrar al-Sham",  "Al-Alami"), ordered = TRUE)
levels(gt$gsubname) 
gt$gname = factor(gt$gname, levels = c(" Taliban", "Islamic State of Iraq and the Levant (ISIL)",  "Shining Path (SL)",   "Farabundo Marti National Liberation Front (FMLN)", "Al-Shabaab",  "Al-Nusrah Front",  "Khorasan Chapter of the Islamic State", "Badr Brigades",  "National Liberation Army of Colombia (ELN)", "Free Syrian Army", "Jaish-e-Mohammad (JeM)", "National Democratic Alliance Army (NDAA-ESSA)", "Lashkar-e-Taiba (LeT)", "Unknown", "Other"), ordered = TRUE)
levels(gt$gname) 
gt$claimmode_txt  = factor(gt$claimmode_txt , levels = c("Personal claim", "Posted to website, blog, etc.", "Unknown", "Call (post-incident)", "Note left at scene", "E-mail", "Other"), ordered = TRUE)
levels(gt$claimmode_txt) 
gt$eventid = as.numeric(gt$eventid)
gt$iyear = as.numeric(gt$iyear)
gt$imonth = as.numeric(gt$imonth)
gt$nperps = as.numeric(gt$nperps)
gt$nperpcap = as.numeric(gt$nperpcap)
gt$nkill = as.numeric(gt$nkill)
gt$nkillus = as.numeric(gt$nkillus)
gt$nkillter = as.numeric(gt$nkillter)
gt$nwound = as.numeric(gt$nwound)
gt$nwoundus = as.numeric(gt$nwoundus)
gt$nwoundte = as.numeric(gt$nwoundte)
gt$latitude = as.numeric(gt$latitude)
gt$longitude = as.numeric(gt$longitude)
summary(gt)
```
