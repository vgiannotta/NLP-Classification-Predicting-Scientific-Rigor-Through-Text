
## Natural Language Processing and Reddit

#### Reddit, ubiquitously dubbed "the front page of the internet," is one of the largest and most comprehensively documented human  conversations of our time.

Frequented by 330 million users monthly, Reddit is home to a multitude of forums and communities for nearly every topic imaginable. This makes Reddit a perfect candidate for NLP (or natural language processing) models, as it is truly representative of the way people communicate through writing day-to-day.

#### Given the prominence of social media as a communication platform, I was curious to test whether a computer could use short-form text compositions to distinguish a substantiated claim from an unsubstantiated one.

The following analysis uses NLP modeling techniques to predict the class of text, taken from one of two subreddits: r/Science and r/EverythingScience. The two subreddits are nearly identical in subject matter; users post articles on news topics relevant to the scientific community. The only major distinguishing characteristic between them is the fact that r/Science requires all posts to be peer-reviewed studies, while r/EverythingScience does not.

#### This analysis will take the following steps to investigate the predictive power of text :

- Query post data from the Reddit API.
- Clean and transform the text data into a suitable format for modeling in SciKit Learn.
- Build and fit multiple NLP models, using only the text from each Reddit post as the predictive variable.
- Assess whether the model was successful in distinguishing substantiated claims from unsubstantiated ones.
- Examine the strongest text influencers on model performance, and establish next steps for a second iteration of this experiment.

### Insights

While the models do improve on baseline accuracy in their ability to make predictions, their performance could be improved. This report concludes that text alone is not the best indicator of class.

Guidelines for future modeling experimentation:

-   Test the models on many kinds of subreddits, not just like ones.

-   Incorporate additional features into the X variable.

-   Format / transform documents prior to model fitting.		

### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**author**|*object*|df|The Reddit username for the author of the post.|
|**domain**|*object*|df|Domain name of the linked article in the post.|
|**num_comments**|*int*|df|The number of comments for the post.|
|**title**|*object*|df|Text portion of the post.|
|**subreddit**|*object*|df|Class of Reddit post. Values are either "Science" or "EverythingScience".|
|**url**|*object*|df|Url of linked article in the post.|
|**subreddit_class**|*int*|df|Binary column for subreddit class. Science = 1, EverythingScience = 0.|
|**word_count**|*int*|df|Number of distinct words in the post. Includes stopwords.|
|**num_stopword**|*int*|df|Number of stopwords in the post.|
