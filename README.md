# state_metrics
An attempt to rank the 50 states in the U.S. to truly find the top of the top.

# Background

I'm ultimately interested in using as much data as possible to figure out what is the best city / neighborhood overall. That's a pretty tall order honestly, so I think it will be easier to just start with the states! So there's all types of ways that states get ranked "top happiness", "most affordable" etc. lots and lots of these types of rankings. What I'm primarily interested in knowing is are there states that just crush in these lists and could make their way to the top of the top of some sort of list of lists?? The metrics themselves tend to be pretty objective, but their relative importance and even the interpretation of what it means to be at the top or bottom is quite subjective. Nevertheless, my goal is to gather as many of these lists as posible! THe nice thing about using states is that it shouldn't be too hard to find lists that rank all 50 states (which might be harder for cities) so we will end up with a nice and neat 50 x N matrix of rankings. From that ranking, the two primary things I would like to do are to cluster (or even some fancy dimensionality reduction) the rankings and see how the states group relative to metric type / region .  Then ultimately I'd like to see whose average  rank is the highest overa ll and across metric types and regions.

# Data sources

I'm pretty sure the U.S. census will be a  huge source of data for me.. but I'm sure there will be others!

I'll list them out individually below and note the recommended ways of accessing the data.

## Census

For accessing Census data it seems like I have two options

- [censusdata](https://github.com/jtleider/censusdata/tree/master)
    - supports census ACS and summary up until 2018?
    - should be pretty plug and play, goes directly to pandas
- [census API](https://www.census.gov/content/dam/Census/data/developers/api-user-guide/api-guide.pdf)
    - needs an API key
        - understandable.. but I really need to figure out how to go about pushing public things that use API keys?? I guess maybe I can keep all the data gathering or even some sort of secrets file in the .gitignore??? Does github have secrets management???
    - otherwise is basically just regular API as usual. Will probably take a bit of work wrangling the data to what I really want.
- [csv dumps??](https://www2.census.gov/programs-surveys/)

# Metric types

So I don't really know the  best ontology _a priori_ for the metric classes of interest.. but I do know that the 7 dimensions of wellness are probably a good starting place!

1. mental
2. physical
3. social
4. financial
5. spiritual
6. environmental
7. vocational

Hmm.. yeah I'll chew on that a bit more. I think these are ones that come to mind 

- climate (environment + weather)
- jobs / entrepreneurship
- education
- recreation
- home ownership

There's definitely more.. a good start though.

# Data organization

So I'm assuming that these lists will be found one metric at a time and will probably vary by year and maybe month. So I just want to create a directory `data` with subdirectories for each year and a flat CSV that has the name of the metric in the filename? Yeah there has to be better ways f doing that, but we have to learn somewhow!! 

I'm also thinking accessing the data will be through a finniky web access protocol, so having the data aggregated in some sort of way would be nice!