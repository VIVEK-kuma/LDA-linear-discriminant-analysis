###LDA-linear-discriminant-analysis
i have prepared this task as a challenge problem given by Eluvio company in their selection process
Since this was an open problem so i have done some analysis of this data and tabulated my finding in thus file along with the code 

->IN this data i have tried to address these problems
What are the total no and types topics in the news titles?
Because news is inherently sequential and temporal, I want to know how the topic evolve over time. In other words, what happened, when and how long did it last?

-> DIFFRENT STEPS AND PROCESS THAT I HAVE USED HERE IN THIS ARE:

1.Preprocess the news titles for LDA model
2.Determine the number of topics using topic coherence score
3.Fit LDA model for all news titles and return the topics
4.Link the topics at consecutive time based on Hellinger distance

->MY OBSERVATIONS:

1.The best number of topics for all news titles, which achieves highest coherence socre is 14.

2.The topics found by LDA make a lot of sense observing the returned words distribution. For example,

  a.Topic: 1, Words: 0.046*"russian" + 0.026*"russia" + 0.023*"iraq" + 0.022*"putin" + 0.019*"milit" + 0.017*"forc" + 0.014*"state" + 0.013*"strike" + 0.013*"say" + 0.013*"troop"

  b.Topic 1 should be Russian military activities in the Middle East.

  c.Topic: 9, Words: 0.092*"kill" + 0.036*"attack" + 0.034*"bomb" + 0.023*"peopl" + 0.023*"polic" + 0.022*"dead" + 0.016*"citi" + 0.016*"suicid" + 0.013*"injur" + 0.012*"blast"

  d.Topic 9 should be terrorist attacks
3.As for the evolvement of topics, I only consider the news titles in 2016 for simplicity. This idea can also scale up to the entire dataset. The main procedure is to find the topics for each month and link similar topics for consecutive months. We say two topics are similar if the Hellinger distance between them is smaller than some pre-specified threshold.

  a.There was a topic chain lasting about 4 months, starting in February and ending in June. This topic is mainly about Syrian refugee.

  b.The news topics in different months are actually quite different in terms of the word distributions. So the threshold has to be set high to construct the links
 
 TOPIC  AND LIBRARY THAT I HAVE USED IN THIS 
gensim: LDA

gensim: Distance Metrics

Topic Modeling and Latent Dirichlet Allocation (LDA) in Python

Topic Modeling in Python

Evaluate Topic Models: Latent Dirichlet Allocation (LDA)


