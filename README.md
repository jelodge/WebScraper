# WebScraper

##### Abstract

We set out to investigate whether there was a relationship between the geographical location of a job posting on a market-leading jobs board and its advertised salary, where salary information was available (a large proportion of salaries are not disclosed on such job postings).

Initially we tried to gauge the relationships between locations and salaries and found there to be strong evidence of meaningful and potentially predictable relationships amongst higher paying roles, but correctly predicting lower end salaries was much more difficult with the information we had available.

Adaptations were made to our initial model to include other variables in our search, where we carried keyword searches relating to seniority of roles, including ones that specified roles were junior as we believed this would be a good way to provide more insight and increase our ability to delineate lower paying roles from higher paying ones.

This did indeed result in a better overall result, although the improvements were only modest. Given the methodology followed during this investigation, we can say that predictions we will be currently able to make will be an improvement on randomised guessing - but further refinements and extra information - particularly around the low salary roles - would be a key avenue for improving our ability to correctly classify job salaries going forward.

##### Methodology

We utilised web scraping technology - whereby a piece of code routinely downloads information from publicly available websites - to aggregate a large number of individual job postings (ensuring duplicates had been removed) and categorised each job's location, remote working status, salary, job title and company name.

Once this data had been collected and cleaned (as information is often duplicated or missing, especially salaries as mentioned earlier), we analysed how the range of salaries were distributed versus the number of job postings within each given range of salaries. What was initially apparent was the roughly bell-curve shaped distribution with a long tail towards the higher-end of salaries.

We modelled these relationships by analysing which locations had the most job postings in the high and low salary bands (categorised as being above or below the median of our sample set in this case) and then trying to assess the probability of a job posting being either in the high or low salary classification, based on its location and the salaries of other such jobs in that location, and therefore make predictions based on the outcome with the highest likelihood, according to what was suggested by the dataset we had available from our web scraping exercise.

The long and thin tail over the higher range of salaries meant that high salary data was less densely packed, and therefore more easily demarcated and subsequently classified. However, the bulk of the data being concentrated within a fairly narrow range of salaries lower in the overall range made classifying the remaining mostly lower salary job postings more difficult, even initially resulting in one of the models we tested only slightly outperforming randomised approximation.

We ultimately needed more contextualised and granular information about these roles to be able to improve on our delineation of whether or not they fell into either the high or low salary classification.

Introducing further categories relating to whether the job title had certain keywords in (junior, graduate, senior, manager) provided some of this necessary clarity, and unsurprisingly the two new categories we introduced that you might logically expect to be at the lower end of the salary range (junior and graduate) did indeed hold a strong importance within our models. This reassured our initial base assumption that further context to the lower end of salaries was likely where the most quick and easy gains were to be made in regards to improving accurate predictive power by offering additional methods of classifying a job posting's most likely salary classification within the lower and more densely packed region.

We then ran several optimisation techniques through the models we had trained on the data, ensuring that they were robust by also testing on unseen data and cross validating results rigorously to make sure we were not causing our model to be overly sensitive to known data, and ergo less effective against new unseen data. The resultant accuracy score we obtained suggested our model was 0.71, or 71%, suggesting it could correctly guess the salary classification (either above or below the sample median value) 7 times out of every 10.

##### Improvements

Of course a larger dataset and a longer timeframe to run the tools necessary to download the information from the web in the first place (as trying too much, too fast can result in being temporarily blocked) would be helpful, as the more data we have the more confidence we can have in our results.

Further dimensions being added to the job postings is another avenue where we could see some meaningful improvements, adding further keyword searches and phrases referring to the amount of prior experience needed, specific programming languages or other software being targeted in the job posting, for example.

The selection of models also performed different in different domains of the data, so given time to optimise a combination of different models, each being utilised within their best range of the data, we could end up with a more capable ensemble approach.

##### Conclusions

We ultimately arrived at a model which was notably more capable of identifying whether a role would be above or below the median salary level for our given sample than random approximation, although in its current form caution should be advised in being overly reliant on it as being incorrect 30% of the time can clearly cause significant issues depending on the context of the deployment of the model.

It should also be noted that if there were tolerances or biases that were of no consequence to a specific goal then further adjustments can be made to maximise various different criteria of the model. For example, should you be comfortable/should your business purpose have the necessary tolerance to accidentally classify below median salary roles as above median salary roles as a trade off for ensuring you classified as many truly above median salary roles correctly as practically possible, then adjustments can be made to such an effect (and vice versa, naturally).
