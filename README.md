# acceptTime

![ggplot_time_to_acceptance_last_180d](https://github.com/isturgill/acceptTime/assets/51013120/13335354-bf95-4f15-bd3e-f0567b274cad)


| Journal abbreviation	| Journal full name |	Number of articles |	Median time to acceptance |
| ------- | ---------------- | ------------- | ---------------------- |
| pmed |	PLOS Medicine |	53 |	198.0 |
pcbi	| PLOS Computational Biology |	344 |	191.0 |
pbio	| PLOS Biology	| 173 |	190.0 |
pdig	| PLOS Digital Health |	87 |	177.0 |
pgph	| PLOS Global Public Health |	492 |	176.0 |
pstr	| PLOS Sustainability and Transformation |	12 |	171.0 |
pwat	| PLOS Water | 48 |	168.0 |
pclm	| PLOS Climate |	47 |	164.0 |
pntd	| PLOS Neglected Tropical Diseases |	329 |	155.5 |
pgen	| PLOS Genetics |	192 |	154.0 |
pone	| PLOS ONE |	6596 |	153.0 |
ppat	| PLOS Pathogens |	253 |	143.0 |


This is the project repository for acceptTime, which has the goal of assessing the time elapsed from submission to acceptance of a manuscript submitted to any PLOS journal. I am not in any way affiliated with PLOS or any of its journals.

## Overview
PLOS supplies several different methods of interacting with article data from their collection of journals -- see [here](https://api.plos.org/text-and-data-mining.html). 

I used their Python module [allofplos](https://github.com/PLOS/allofplos) to download the full collection of PLOS XML articles: a total of 347,607 and taking up about 38GB as of the time of downloading on 11/26/2023. 

XML data were parsed and extracted using [xmltodict](https://pypi.org/project/xmltodict/), documented in the acceptTime_xml_extract.ipynb Juypter Notebook. Processed data were saved as 2023-11-29_plostime_data.txt. 

Analyses and visualizations of acceptance times were documented in the acceptTime_analyze.ipynb Jupyter Notebook and acceptTime_analyze.Rmd R markdown document.

> [!NOTE]
> A small number of articles had negative computed values due to nonsensical date values in some older XML documents. When looking at more recent articles (e.g. last 180 days), these no longer show up. There are also very low time to acceptance values like 0 days or 1 day, but spot-checking suggests these are true values and perhaps represent rare and special cases. Examples below: \
> \
> [-2053 days to acceptance](https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.0040325) \
![image](https://github.com/isturgill/acceptTime/assets/51013120/678d41fd-6cf7-4abf-92ca-b641ea366424) 
> 
> [0 days to acceptance](https://journals.plos.org/plosntds/article?id=10.1371/journal.pntd.0004517) \
![image](https://github.com/isturgill/acceptTime/assets/51013120/755ee23a-641c-46eb-b87b-3010c0656ec4)

