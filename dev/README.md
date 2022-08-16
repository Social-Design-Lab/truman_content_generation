# For Developers

# Ideas to improve this project

## generate_actors.ipynb

1. Allow the user to set distributions or ranges for various categories. For example, allow them to...
    1. specify an age range
    1. set a gender distribution
    1. specify a country or distribution of regions
    1. set a distribution for the `class` column. (Right now, it is only adds 'normal' to every actor in the list and assumes the user will fill it in by hand.)        
    **Note: Some of these might require different API(s) or methods instead of or in addition to the ones in use. For example, if the user would like to include any non-binary genders, a dictionary with distributions or another API would need to be used.**
1. Make usernames less "cookie-cutter". Have more variation instead of just a word or two followed by a number

## generate_posts.ipynb

1. Allow the user to set distributions or ranges for various categories. For example, allow them to...
    1. set a distribution of how often actors post. For example, 10% of actors post 60% of the time.
    1. set a distribution of time. For example, 80% of the posts are from before the beginning of the simulation.
    1. set a distribution for `class` and `experiment_group`
1. Improve image search
    1. find better method to pull out keywords or phrases to search for
    1. Use a different API, or multiple APIs
        1. Google Image search is ideally the best given the size of its library. The issue I ran into was when filtering by images available for commercial use. This severely limited the library. Also, the Google Image search API I was using often returned images that had absolutely no relation to the text, even significantly worse than Pexels does at its worse.
1. Develop an option to start with an image and pull out keywords and phrases to generate a sentence, instead of starting from text generation. This would likely help with the accuracy of images relating to text. 
1. Allow for csv input. That way a user can input a Truman posts.csv file and have this program add n addition posts similar to what was already given.
1. Allow for input from other sources like Facebook, Instagram, etc.

## In general

1. Add notebooks to generate the other csv files (`replies.csv`, `actor_replies.csv`, and `notifications.csv`)
    1. For comments, one idea might be to use GPT-Neo in a similar way to how it is used to generate post text. The format of the input to the model might be:
        ```
        Post: This is a post
        Comment: This is a comment
        ###
        Post: This is a post
        Comment: 
        ```
        The model would then return a comment (in theory). There could be multiple full examples of posts and comments, just like there are when generating posts. These examples could come from generated text or could be manually entered by the user. Also, if you'd like to dive even deeper for this, another idea might be to use a computer vision library to get the subject(s) of each image and use those in this prompt as well. 

