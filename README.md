Avast Enterprise Data Hackathon
====

Raw CSV samples are [here](https://github.com/hackathonBI/Avast/tree/master/sample%20data).


## data sample description

Hello we're providing you data that may look really strange on the first sight.

In fact there is only three columns:

1. **id** - anonymized UID of the user
2. **target** - whether the user had to deal with suspicious content or not
3. **all_params** - an array of 7434 boolean parameters/indicators of various machine collected behaviour (first 4126) and machine state (rest 3311).


|id|target|all_params|
|---|---|---|
|1|1|{1,1,1,1,0,0,0,1,1,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|2 |0	 |{1,1,1,1,0,1,0,1,1,0,0,1,0,0,0,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|3 |0	 |{1,1,1,1,0,0,0,1,0,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|4 |0	 |{1,1,1,1,0,0,0,1,1,1,0,1,0,0,1,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|5 |0	 |{1,1,1,1,0,1,0,1,1,1,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,1,0,0}|
|6 |0	 |{1,1,1,1,0,0,0,1,1,0,0,1,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|7 |0	 |{1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|8 |1	 |{1,1,1,1,0,0,0,1,1,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|9 |0	 |{1,1,1,1,0,0,0,1,0,0,0,1,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|

|id|target|all_params|
|--|------|----------|
|1 |1	 |{1,1,1,1,0,0,0,1,1,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|2 |0	 |{1,1,1,1,0,1,0,1,1,0,0,1,0,0,0,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|3 |0	 |{1,1,1,1,0,0,0,1,0,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|4 |0	 |{1,1,1,1,0,0,0,1,1,1,0,1,0,0,1,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|5 |0	 |{1,1,1,1,0,1,0,1,1,1,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,1,0,0}|
|6 |0	 |{1,1,1,1,0,0,0,1,1,0,0,1,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|7 |0	 |{1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|
|8 |1	 |{1,1,1,1,0,0,0,1,1,0,0,0,0,0,1,0,0,1,0,0,... many other rows here ...,0,0,0,0,0}|
|9 |0	 |{1,1,1,1,0,0,0,1,0,0,0,1,0,0,0,0,0,0,0,0,... many other rows here ...,0,0,0,0,0}|

We are presenting part of the normal dataset. The task is in fact much bigger, but we reduced the dataset to one region only. So we've helped you a bit from the start, as the behaviour, states and target correlation is in fact very different across the globe.

We at Avast try to use this kind of datasets to identify whether the device is likely to get infected or not, which could help the software in the future to be more cautious on such devices and decrease the risk of malware or virus infection (enable shields to be more/less aggressive). 

The problem you will face working with this data (beside the fact that they are huge) is that they are relatively sparse, that means that most of the boolean parameters are zero. The classification is usually performed by different data mining methods such as logistic regression or trees. It also has been shown that classification algorithms can be improved (in terms of quality and speed) by grouping some parameters together (ie. creating categories) using functions SUM, AND, OR, etc. The number of the indicators and hence the huge number of all possible combinations is the major problem for this kind of grouping.

So what we are looking for:
- dimensionality reduction
- feature selection
- feature extraction
- feature categorization (all based on target variable).
