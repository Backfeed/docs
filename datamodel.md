# REST API Data Model 

No formal definition, just some examples, to have some reference for discussion

The idea is that this is what the API will return,  but it also serves as a 
guideline for variable naming in the code.

In general:

* All 'reputation' values are expressed as fractions of the total reputaiton of the system
* Tokens are just absolute values (not fractions)

## User

A user has tokens and reputatation:

    {
       'id': 123,
       'tokens': 11.3,
       'reputation': 0.03, /* the fraction of the user' rep
       		wrt the total_repution */
    }


## Contribution

	{
		'id': 12345,
		'contributor' : {
			/* user structure */
			...
		},
		'score': 0.30, 
            /* score = the sum of the reputation
			of the 'up votes' as a fraction of total_reputation (and in general sum(evalutor.reputation * evaluation.score)) */
		'engaged_reputation': 0.4, 
            /* the sum of the reputation of all evaluators of this contribution */
	}


* in the present API, 'score' is an absolute value, and 'scorePercentage' the 
fraction of the 'score' relative to total_repuation. I think this is confusing.
* question, ore: why do you have 'score' and 'scorePercentage'?


## Evaluation

	{
		'id': 1234545,
		'value': 1.0,
		'evaluator' : {
			/* user structure */
			...
		}
		'contribution': {
			...
		},
	}