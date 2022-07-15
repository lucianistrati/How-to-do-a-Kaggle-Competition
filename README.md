# How-to-do-a-Kaggle-Competition

This repository contains some advice on how to do a Kaggle Competition. As an example you can checkout the following competition I created a couple of months ago https://www.kaggle.com/competitions/nitro-lang-processing-1/overview (which served as the task for Nitro Language Processing Hackathon 2022 Edition). I added all the ".MD" files and the datasets I used to create that competition in the "data" folder, so that you can check them up and try to replicate my work if you want to test out your knowledge create a demo competition. 

# General steps to follow prior to creating the competition itself

1. Figure out who is going to be the competitors in your contest
2. Think of a task that could be feasible both in terms of your participants skills and interests
3. See if there already exists a dataset for that task, if there is not try to make one, otherwise go back at step 2 and think of another task
4. Hooray, it seems you have the dataset and the task, now you have to make sure that the dataset labels won't be easily found by your participants (assuming you are doing a supervised learning task, if the task is unsupervised, just be sure there are no gold-standard predictions)
5. However if the labels already exist, check out with somebody else how is easily it is for them to find
6. If it is very easy to find, there are some tricks you could try such as renaming your labels, using just parts of the data by eliminating datapoints, adding datapoints, removing datapoints with certain labels entirely, change the format of the data (i.e. from csv to json or from json to xml)
7. Lastly, you would want to benchmark and try out several models just to make sure that your task is both approachable and that creativity allows talent & hard work to shine in the competition leaderboard.

# Useful links with steps to create the competition itself after figuring out the task and the data

- https://www.kaggle.com/code/alexisbcook/getting-started-with-kaggle-competitions/notebook
- https://www.kaggle.com/docs/competitions
