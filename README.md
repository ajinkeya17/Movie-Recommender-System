# End to End Movie Recommendor System

## Dataset Used : TMDB 5000 movies Dataset (https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

## Options for Recommendor Systems : Content based vs Collaborative Filtering based. 
We used Content based modelling. Where a tag is created for each movie which represents it's comprehensive feature space. In our project we combined multiple textual columns such as actors of te movie,director,overview,etc to create a single textual tag of the movie which describes it the best. This textual tag is converted to a numeric vector. The similarity between each movie and all the others are calculated based on cosine similarity of these vectors. A gradio based interface was created where one can input any of the 4806 movies of the dataset and it will output the 5 most relevant/simmilar recommendations.

# Steps:
1.) Run the Movie Recommendor model python notebook. 
- This file will pull and merge the tbmd 5000 credits and tmdb 5000 movies dataset. 
- We clean the data and form the movie-tag mapping. Where each tag is just the combination of the relevant textual features that would help describe and characterize a person's preference for the particular movie best.
- Post this we do preprocessing(stemming, stop word removal) on tags before vectorizing them. 
- We use bag of word technique for vectorization. 
- We then compute the similarity score for each movie with all other movie vectors using cosine similarity measure
- We conduct inferencing
- We pickle the vectors and the final cleaned dataset as these two components are needed for inferencing/prediction to be used by our next file (These files are not included in our repo as they are significantly large and hence we have .pkl in our .gitignore file. But when we run our model notebook the pickle files will get created in the repo)

2.) Run the Gradio Movie Recommendor Interface python notebook
- Once the vectors and cleaned data is pickled in the final steps of the above notebook they are pulled in this notebook
- The inferencing/predicition/recommendation function is copied from above notebook
- Custom Gradio interaface is created and user can input any of the 4086 movies in our dataset and get the 5 closest recommendations (see the png file for how the sample output looks)



Can refer to : https://www.youtube.com/watch?v=1xtrIEwY_zY for detailed explanation of the steps
