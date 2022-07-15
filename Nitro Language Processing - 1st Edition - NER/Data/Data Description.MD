# - Task
In the Named Entity Recognition (NER) task, the participating teams will have a task of classifying each token from a sentence.
The problem has several implications and use cases, including information extraction, event extraction, text summarization and feature extraction. NER models are currently employed in many industries such as: finance, law, HR or social media monitoring.

# - File descriptions
- train.json - the training set
- test.json - the test set
- sample_submission.csv - a sample submission file in the correct format
- random_seed_setter.py - a python file showing how to set up random seeds in a couple of packages
- tag_to_id.json - mapping of the ner tags to ner ids
- teams_rand_seed.csv - the file containing the random seeds of each team

# - Data Format
The dataset is a list of instances. The following in an instance of the training dataset:

{

'ner_tags': 
    ['O', 'GPE', 'O', 'O', 'O', 'O', 'O', 'O', 'LOC', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'PERSON', 'O', 'O', 'O', 'O', 'PERSON', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'PERSON', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'PERSON', 'O', 'PERSON', 'O', 'PERSON', 'O', 'O', 'PERSON', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O', 'O'],

'ner_ids':
    [0, 3, 0, 0, 0, 0, 0, 0, 4, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0], 'tokens': ['În', 'România', ',', 'ca', 'de', 'altfel', 'în', 'întreaga', 'Europă', ',', 'stand', 'up', '-ul', 'este', 'forma', 'de', 'divertisment', 'cea', 'mai', 'îndrăgită', 'de', 'tineri', 'în', 'acest', 'moment', ',', 'comediantii', 'reușind', 'să', 'umple', 'săli', 'care', 'erau', 'destinate', 'mai', 'degrabă', 'artiștilor', 'din', 'zona', 'muzicii', 'pop', 'rock', ',', 'iar', 'Badea', ',', 'Bordea', 'și', 'Micutzu', 'sunt', 'printre', 'cei', 'care', 'au', 'contribuit', 'direct', 'la', 'succesul', 'acestei', 'forme', 'de', 'divertisment', 'în', 'țara', 'noastră', '.'],

'space_after':
    [True, False, True, True, True, True, True, True, False, True, True, False, True, True, True, True, True, True, True, True, True, True, True, True, False, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, False, True, True, False, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, True, False, False]}f

# - Data Fields
The fields of each training example are:
tokens are the words of the sentence
ner_tags are the string tags assigned to each token.
ner_ids are the integer encoding of each tag
space_after is used to help if there is a need to detokenize the dataset. A true value means that there is a space after the token on that respective position

# - Labels
The corpus was annotated with the following classes:

PERSON - proper nouns, including common nouns or pronouns if they refer to a person. (e.g. 'sister')

GPE - geo political entity, like a city or a country; has to have a governance form

LOC - location, like a sea, continent, region, road, address, etc.

ORG - organization

LANGUAGE - language (e.g. Romanian, French, etc.)

NAT_REL_POL - national, religious or political organizations

DATETIME - a time and date in any format, including references to time (e.g. 'yesterday')

PERIOD - a period that is precisely bounded by two date times

QUANTITY - a quantity that is not numerical; it has a unit of measure

MONEY - a monetary value, numeric or otherwise

NUMERIC - a simple numeric value, represented as digits or words

ORDINAL - an ordinal value like 'first', 'third', etc.

FACILITY - a named place that is easily recognizable

WORK_OF_ART - a work of art like a named TV show, painting, etc.

EVENT - a named recognizable or periodic major eventdaca nu iti da codul 

O - other, none of the above classes


# - Training Data
There are 12330 datapoints in the training set (train.json file). Each training datapoint has the fields: tokens, ner_tags, ner_ids and space_after. 

# - Test Data
There are 2421 datapoints in the test set (test.json file). Each testing datapoint has the fields: tokens and space_after (just the ner_ids will be predicted, since they are essentially the same thing as the ner_tags). 

# - Submission sample
The sample submission (sample_submission.csv file) will contain roughly 76.000 lines, because there 76.000 tokens in the 2421 documents from the test set. You can look at this as a liniarized matrix of the tokens (listing the tokens of each document from beggining to the end of the test.json file, from the begging to the end of the sentence). It will have two columns: Id and ner_label. Id is the unique identifier for each token. ner_label will be a int value from 0 to 15 (the 0 - Other class is included). The labels from sample_submission.csv are random and serve just the purpose of showcasing how a submission should look like.

# - Please bear in mind that for the current leaderboard just 50% of the testing data will be used, at the end of the competition the rest of the 50% will be used for the final leaderboard. 

# - Data is generally in Romanian, but there might some noisy parts in other languages here and there.
