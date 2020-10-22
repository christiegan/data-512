## README

#### Goals: 
Examine the aggression dataset to see if there is a bias between different demographics of label workers when labelling aggression. Examine the aggression and toxicity datasets for a difference in biases, if any, between labelling toxicity and aggression among different demographics of label workers.

#### Data Sources:
Perspective API
CC0 license

[Conversation AI](https://conversationai.github.io/)
[Aggression Dataset](https://figshare.com/articles/dataset/Wikipedia_Talk_Labels_Aggression/4267550)
[Toxicity Dataset](https://figshare.com/articles/dataset/Wikipedia_Talk_Labels_Toxicity/4563973)

Context Readings:
[Research Project:Detox](https://meta.wikimedia.org/wiki/Research:Detox)
[Research: Detox/Data Release](https://meta.wikimedia.org/wiki/Research:Detox/Data_Release)
[Conversation AI](https://conversationai.github.io/)

Citations:
Wulczyn, Ellery; Thain, Nithum; Dixon, Lucas (2017): Wikipedia Talk Labels: Personal Attacks. figshare. Dataset. https://doi.org/10.6084/m9.figshare.4054689.v6

Wulczyn, Ellery; Thain, Nithum; Dixon, Lucas (2017): Wikipedia Talk Labels: Aggression. figshare. Dataset. https://doi.org/10.6084/m9.figshare.4267550.v5

Thain, Nithum; Dixon, Lucas; Wulczyn, Ellery (2017): Wikipedia Talk Labels: Toxicity. figshare. Dataset. https://doi.org/10.6084/m9.figshare.4563973.v2

Wulczyn, Ellery; Thain, Nithum; Dixon, Lucas (2017): Wikipedia Talk Corpus. figshare. Dataset. https://doi.org/10.6084/m9.figshare.4264973.v3

Wulczyn, Ellery; Thain, Nithum; Dixon, Lucas (2016): Wikipedia Detox. figshare. doi.org/10.6084/m9.figshare.4054689
Retrieved: 13 00, Oct 31, 2016 (GMT)

#### Final CSV details:
##### Aggression:
* rev_id: MediaWiki revision id of the edit that added the comment to a talk page.
* worker_id: Crowd-worker id.
* aggression_score: Categorical variable ranging from very aggressive (-2), to neutral (0), to very friendly (2).
* aggression: Indicator variable for whether the worker thought the comment has an aggressive tone . The annotation takes on the value 1 if the worker considered the comment aggressive and value 0 if the worker considered the comment neutral or friendly.
* comment: Comment text. Consists of the concatenation of content added during a revision/edit of a talk page. MediaWiki markup and HTML have been stripped out. To simplify tsv parsing, \n has been mapped to NEWLINE_TOKEN, \t has been mapped to TAB_TOKEN and " has been mapped to `.
* year: The year the comment was posted in.
* logged_in: Indicator for whether the user who made the comment was logged in. Takes on values in {0, 1}.
* ns: Namespace of the discussion page the comment was made in. Takes on values in {user, article}.
* sample: Indicates whether the comment came via random sampling of all comments, or whether it came from random sampling of the 5 comments around a block event for violating WP:npa or WP:HA. Takes on values in {random, blocked}.
* split: For model building in our paper we split comments into train, dev and test sets. Takes on values in {train, dev, test}.
* gender: The gender of the crowd-worker. Takes a value in {'male', 'female', and 'other'}.
* english_first_language: Does the crowd-worker describe English as their first language. Takes a value in {0, 1}.
* age_group: The age group of the crowd-worker. Takes on values in {'Under 18', '18-30', '30-45', '45-60', 'Over 60'}.
* education: The highest education level obtained by the crowd-worker. Takes on values in {'none', 'some', 'hs', 'bachelors', 'masters', 'doctorate', 'professional'}. Here 'none' means no schooling, some means 'some schooling', 'hs' means high school completion, and the remaining terms indicate completion of the corresponding degree type.

##### Toxicity:
* rev_id: MediaWiki revision id of the edit that added the comment to a talk page.
* worker_id: Crowd-worker id.
* toxicity_score: Categorical variable ranging from very toxic (-2), to neutral (0), to very healthy (2).
* toxicity: Indicator variable for whether the worker thought the comment is toxic. The annotation takes on the value 1 if the worker considered the comment toxic and value 0 if the worker considered the comment neutral or healthy.
* comment: Comment text. Consists of the concatenation of content added during a revision/edit of a talk page. MediaWiki markup and HTML have been stripped out. To simplify tsv parsing, \n has been mapped to NEWLINE_TOKEN, \t has been mapped to TAB_TOKEN and " has been mapped to `.
* year: The year the comment was posted in.
* logged_in: Indicator for whether the user who made the comment was logged in. Takes on values in {0, 1}.
* ns: Namespace of the discussion page the comment was made in. Takes on values in {user, article}.
* sample: Indicates whether the comment came via random sampling of all comments, or whether it came from random sampling of the 5 comments around a block event for violating WP:npa or WP:HA. Takes on values in {random, blocked}.
* split: For model building in our paper we split comments into train, dev and test sets. Takes on values in {train, dev, test}.
* gender: The gender of the crowd-worker. Takes a value in {'male', 'female', and 'other'}.
* english_first_language: Does the crowd-worker describe English as their first language. Takes a value in {0, 1}.
* age_group: The age group of the crowd-worker. Takes on values in {'Under 18', '18-30', '30-45', '45-60', 'Over 60'}.
* education: The highest education level obtained by the crowd-worker. Takes on values in {'none', 'some', 'hs', 'bachelors', 'masters', 'doctorate', 'professional'}. Here 'none' means no schooling, some means 'some schooling', 'hs' means high school completion, and the remaining terms indicate completion of the corresponding degree type.

#### Special considerations: 
* The language is all in English, but commenters may come from anywhere around the world.
* Aggression scores range from -3 to 3, while Toxicity scores range from -2 to 2
* I turned the ID columns into indices. 