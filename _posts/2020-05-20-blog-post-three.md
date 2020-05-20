---
layout: post
title: Using PyTorch for Toxic Content Monitoring with FastText, FastAPI and Docker
tags: [history, economics, plotly]
---

![cover](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/bitmap.png)

<p style="text-align: justify;">
In recent years tools for studying online behavior have increased in popularity in both industry and academia. One area of active study is negative online behavior, e.g. comments which are offensive enough that participants would be compelled to leave the conversation. Prior models were error prone and didn’t allow for stakeholders to pick the type of toxicity they were interested in finding, i.e. some models monitor profanity but not other types of offensive behavior. The following article presents a multi-headed model capable of detecting numerous types of toxicity, i.e. threats, obscenity, insults and identity based threats. The dataset used to train the model is provided by Wikipedia’s talk page edits. The following graphic is a breakdown of the dataset into various categories our model will be predicting
</p>

![boston](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/texic.png)

<p style="text-align: justify;">
The final model produced an F1 score of 0.753 and an ROC-AUC score of 0.987. I am using a Bi-directional LSTM + GRU neural network made with PyTorch, FastText vectorization, a FastAPI framework and deploying using a Docker image.
</p>

![merrimack_mill](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/Merrimack_Mills_1850.gif)

<p style="text-align: justify;">
The firms of the Massachusetts-type, modeled after the Boston Manufacturing Company, were located on major rivers of northern New England. Generally capitalized in excess of $500,000, these were typically multi-factory operations. From the beginning, Massachusetts-type firms were fully integrated facilities producing units heavily concentrated in low-count goods or goods that drop in demand when consumer income rises. Massachusetts-type firms were responsible for the majority of textile producing from 1825–60 measured in yards.
</p>

![mass-type](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/mass_type.png)

<p style="text-align: justify;">
The image above shows the amount of yards of textile produced per county in the New England area. Production was concentrated in a few counties.
</p>

![slater_mill](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/1_DoDaKM4J_sYdMW_AN5Unfw.jpeg)

<p style="text-align: justify;">
Rhode Island-type firms, existed along side the Massachusetts-type in much a much higher number of operations. Rhode Island-type mills were small, often specialized, and tended to produce medium grade cloth. These firms were responsible for a relatively small amount of total textile production from 1825–60 measured in yards. The image below shows the amount of yards of textile produced per county in the New England area.
</p>

![rhode_type](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/ri_type.png)

<p style="text-align: justify;">
The distribution of these firms were not wholly geographic. In some cases, the firms of Rhode Island-type were located in Massachusetts as well as Rhode Island Connecticut. Company records for at least some of the Massachusetts-type and Rhode Island-type firms exist for at least some part during the antebellum period.
</p>

### Section Two ###
<p style="text-align: justify;">
Increase in productivity by Massachusetts-type firms during the antebellum period resulted in an increase in output per spindle by approximately 50 percent during the 1830’s. In the long run, an upward trend of labor productivity and changes in direction of capital-index around 1840 might suggest innovation prior to 1840 was labor saving as well as capital saving.
</p>

![plot](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/plot1.png)

<p style="text-align: justify;">
It is frequently cited that the American textile industry underwent a revolutionary transformation in the decade between 1814 and 1824, but that thereafter technical progress was relatively slow. The decade saw inventions and widespread innovation of the power loom, Walter dresser, the double speeder and filling frame, self-acting loom temple, number of picker and openers and the increase in spindle speed associated with the innovation of the belt drive. Moreover, new machines do not tell the full story. More important, new refinement were worked out in the machine shop and incorporated in the latest model of machine. In terms of industrial organization, the integrated mill, successfully pioneered by the Boston Manufacturing Company, was widely adopted. The graphic above shows that the industry leaders, i.e. Massachusetts-type, integrated machine shops, which actually developed new machines and improved existing one were able to out product Rhode Island-type mills.
</p>

![panic_of_1857](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/1_naprOpkM2VXN51h-3BDiyw.jpeg)

<p style="text-align: justify;">
The dominant economic event of the late 1850’s was the panic of 1857. Sales and output began to erode early in that year but dropped swiftly during the last half. The year-end inventories were almost twice the level of 1856. The Panic of 1857 was a financial panic in the United States caused by a decline in international trade at a time of over-expansion in the domestic economy.
</p>

<p style="text-align: justify;">
The records of business firms represent a relatively untouched resource which should be of use to study the American economy. This post attempts to make sense of the fluctuations in the cotton industrial output between the Census benchmark years. These records can shed light on the fluctuations in inventories, sales, costs, profits, and for other variables for which there is only benchmark data.
</p>

#### Reference ####
<p style="text-align: justify;">
1. Lance E. Davis and H. Louis Stettler III. The New England Textile Industry, 1825–60: Trends and Fluctuations, pages 213–242. NBER, 1966.
</p>
