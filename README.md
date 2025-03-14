# Data Visualization Final Project 

For my final project in this course, I started a professional website that at the moment only contains a 
data visualization portfolio around my thesis results. My thesis topic is about
the moralization of self improvement, and this work explores it through three different research questions: 

-   RQ 1. Is moral language present when talking about self-improvement?
-   RQ 2. Are there some specific topics within self-improvement discussions that tend to be discussed with a higher moral tone?
-   RQ 3. How does the usage of moral language associate with emotions in the context of self-improvement?

More detail on the topic and the motivation can be found on the website itself.
[Click here to see the data visualization project](https://natashacarpcast.github.io/datavis.html)

## Data

All comments and submissions from three subreddits (r/selfimprovement, r/investing and r/homeowners) were obtained through [Academic Torrents](https://academictorrents.com/details/56aa49f9653ba545f48df2e33679f014d2829c10). 
The original datasets included each entry's id, text, date etc.  

Data cleaning and previous processing were done on earlier stages of my project. 
Main processing included the usage of the  Linguistic Inquiry and Word Count (LIWC) software to calculate morality and emotional scores, 
the use of the [Moral Foundations Dictionary 2.0 (MFD)](https://www.liwc.app/dictionaries) using the same software and the use of a
[MoralBERT classifier.](https://github.com/vjosapreniqi/MoralBERT) 

Topic modeling was also key in the project and it was done using the Gensim library.

More details on all of this steps can be found on my [thesis repository](https://github.com/natashacarpcast/moralization-selfimprovement)

On the [data folder](datavis-files/data) inside the [data visualization project folder](datavis-files)
the following files can be downloaded for directly working on the visualization project:

1) [engineered_data.csv:](datavis-files/data/engineered_data.csv) This file contains the results from the LIWC software used for the first Tableau
plot for RQ1. It was also used for the first Tableau plot for RQ3. 
2) [moral-bert-results-binary.csv:](datavis-files/data/moralbert-result-binary.csv): This file contains the binary designation of Reddit documents to
moral values based on the [MoralBERT classifier.](https://github.com/vjosapreniqi/MoralBERT). It was used for the bottom plot from the Tableau 
dashboard corresponding to RQ1. 
3) [final_data.csv](final_data.csv): This file contains the results from the LIWC software combined with the results from topic modeling, where all documents
are assigned to a single topic. It was used for the visualizatons on RQ2. 
4) [moralwords_bytopic.csv](moralwords_bytopic.csv): This file contains the emotional scores for all moralization words in each topic, calculated by
averaging the scores for each document in which a word appears. It was used for the text plot in RQ3. 

## Software

To reproduce this data visualization project, you'll need:

- Tableau Software
- R Studio, with the following packages:
  - ggplot2
  - dplyr
  - forcats
  - ggtext
  - showtext
  - shiny
  - bslib

## Repository Structure - Important Files

- [_site.yml:](_site.yml) This file contains the professional site's navigation structure
- [custom.css:](custom.css) This file contains CSS customization code for the website
- [datavis-files/data](datavis-files/data): this folder contains data files for the data visualization project
- [datavis.Rmd](datavis.Rmd): this file contains the code for the data visualization page, including one of the plots directly coded and 
Shiny/Tableau embeddings. 
- [datavis.html](datavis.html): this file contains the knitted HTML file for the [datavis.Rmd](datavis.Rmd) page.

## Additional Information

The Shiny app cannot be deployed from a Github Pages repository, so its code can be found independently on 
[its own Shiny apprepository](https://github.com/natashacarpcast/shiny-finalproject-datavis)