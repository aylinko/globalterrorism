# Analysis of Terror in the World
### Aylin Kosar

### Table of contents

- [Introduction](#Introduction)
- [Data](#Data)
- [Analysis](#Analysis)
- [Conclusion](#Conclusion)


## Introduction

Global terrorism affects our world today and is many times portrayed with a misunderstanding of why it occurs. Whenever we hear of a terrorist attack, the news media always dramatizes it to be a larger issue than it really is especially when our country has a big issue with gun violence. Terrorism looks terrible now because of the expanded methods on harming people and the new technology that has arose. However, the ideology and the actual tactics that the group or individual deploys is still the same. The data set contains data from 1970 to 2017. I would like to specifically find out where and when most attacks occur, who is the most targeted, which terrorist group attacks the most, and the nationality of the terrorists. 


## Data 

The data was used was from the National Consortium for the Study of Terrorism and Responses to Terrorism (START), University of Maryland. (2018). The Global Terrorism Database (GTD) [Data file]. Retrieved from https://www.start.umd.edu/gtd". The same data set made public can be found in this Kaggle page https://www.kaggle.com/ecodan/global-terrorism-db/home. The data set contains **181691** observations and **135** variables. Eventually, the data was preprocessed to **167355** observations and **36** variables. 

## Analysis

Chi-square and regression were used to conduct the analysis for the data. The Chi-square resulted in the following

+ May and July were the months that we see many attacks occur
+ Middle East / North Africa region have the most attacks
+ Public places are the common hot spots for terror attacks and the targets are mostly everyday people that do not necessarily have a government job (i.e., Police and   Military)
+ Explosives/ Bombing is the type of attack favored by terrorists
+ 2014 had the most attacks
+ Terrorists prefer to make personal claims rather than claim attacks using media, calls, email, leaving a note at the scene, or other     forms.
+ Police are the most targeted in Afghanistan and had the most personal claims of attacks by terrorists. Iraq is the most targeted with the usage of bombings/explosive attacks.

Using stepwise regression and multiple regression, the variables country, region, type of attack, suicide attacks, target type, nationality of victim/target, individual attacks, perpetrators killed and captured, and the terrorist method of claiming attacks were correlated. However, the regression did not answer the questions that were needed for the analysis. The chi-square was a better method in seeing when the attacks occured and who was the most targeted. The nationality of the terrorists unfortunately were not able to find.

In order to futher investigate, two plots and a map were created. Below are three plots that show the number of fatalities versus the terrorist organization and color coordinated by the region and the target type. ISIL has created the most fatalities with their attacks in the Middle East and North Africa region. They have targeted diplomatic government officials, police, educational institutions, and NGOs.

![plot1](https://github.com/aylinko/globalterrorism/blob/master/Plot%201.PNG)

![plot2](https://github.com/aylinko/globalterrorism/blob/master/plot2.PNG)

Below shows the frequency of the attacks in each region. We see that the Middle East/ North African region has the most attacks. If the markers are clicked further, the details of the attacks can be seen. 

![Map1](https://github.com/aylinko/globalterrorism/blob/master/Map%201.PNG)

![Map2](https://github.com/aylinko/globalterrorism/blob/master/Map2.PNG)

Note: Was not able to upload the leaflet widget on this page. The file for the map can be found in the github page.

## Conclusion 

We can see that most attacks are in the Middle East/North Africa region. The ones who are targeted are everday people that don't have a job as police officer or are in the military. Unfortunately, the nationality of the terrorists were not able to be identified. This would have been helpful to know since we always assume most terrorists are Middle Eastern and that not all are actually of that enationality but could be of any nationality. We know that most attacks occur in May and July. The year 2014 had the most attacks.
