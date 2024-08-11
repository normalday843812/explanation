# explanation

yeah I set up a new project on the console in google cloud then added the "YouTube Data API v3" API. I got an API key from the console and added that to the python file. I imported google-api-python-client to get the data, pandas to add it to a CSV, and tqdm for a progress bar. I also added a global variable for carter's channel ID.

I then implemented a function to fetch a list of all videos from the channel ID (Carter's channel). It used "tokens" because I think that the max amount of results is around 50 and there are many more videos on Carter's channel since a year ago. These tokens made it so that it got 50 at a time then "appended" the results to that last result. The results just had the video ID and title

Once that seemed to work, I made another function to count the amount of comments containing the keywords (those being "thug shake," "thug shaker" and "thug-shake.") It basically was just two variables and a while true to get all comments on each video, then iterate over each comment with regex to see if it contained the keywords. It used "tokens" too like the one to get a list of all videos. If the response from the API didn't contain any more comments then it broke the while true loop.

Then I basically just called those functions and inputted the start date (2023-08-09T00:00:00Z) and end date (2024-08-09T00:00:00Z) with the channel ID. I added a progress bar too because why not. The script stored the video ID, title, and count of thug shake comments in a list then saved it to a CSV file. 
