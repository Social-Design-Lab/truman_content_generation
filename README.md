# Truman Content Generation

*Project by Ryan Schmid*

The contents of this repository allow you to generate fake profiles and posts for the Truman project. It is meant to be a starting point for content creation -- the posts' text and images may not be perfect in all cases and will likely require some manual changes to get them to where they need to be. While it isn't perfect, the idea is to get you, the user, 70-80% of the way to where you want to be.

This document will walk you through all of the steps needed to use this software. 

---

# Step 1. Getting Started

First, let's download the necessary software. 

## Git Bash (Windows)

This was already downloaded in the Truman tutorial, but in case you have not downloaded it, you may do so here: https://gitforwindows.org/

Choose all default options during installation.

## Python

To download and install the latest version of Python, follow the instructions here: https://www.python.org/downloads/

Choose all default options during installation.

To test installation, open a terminal (MacOS) or Git Bash terminal (Windows), and enter the following:

`python --version`

Press "Enter."

If it does not show something like `Python 3.10.6`, follow the instructions it tells you to download Python. Keep testing to see if Python has installed using the command above before moving onto the next step. 

## JupyterLab

To install JupyterLab, our programming environment, enter the following in your terminal and press "Enter":

`pip install jupyterlab`

## Installing Libraries and Dependencies

To install all of the dependencies for this project, copy the line below and paste it into your terminal (MacOS) or Command Prompt (Windows):

```
pip install numpy pandas requests wordfreq random-address tqdm regex nltk Counter transformers
```

To install HappyTransformer (required), use `pip install happytransformer`. If that does not work, try `pip install --upgrade --force-reinstall happytransformer`.

## Cloning from GitHub

Using your terminal, navigate to the desired place to store this project in your file directory. On GitHub, click on the green "Code" button with white lettering, and copy the text in the box to your clipboard. Then, in your terminal, type `git clone ` and then paste the contents of your clipboard. Press "Enter."

Type in `cd ` followed by the name of the project folder. 

## Open in JupyterLab

Now, open the project in JupyterLab by entering `python3 -m jupyterlab` into the terminal. A new browser tab should open with the JupyterLab workspace.

### File structure

- .gitignore - file containing files and folders to not be saved to the repository
- dev - contains notes for developers, including a README that describes ways to improve this project.
- internal - used for storing the models and some miscellaneous data
- output - for generated output files
- 2_download_models.ipynb - code for downloading the models used in generating content
- 3_generate_actors.ipynb - code for generating profile data and images
- 4_generate_posts.ipynb - code for generating post data and images

---

# Step 2. Download models

Open the file `2_download_models.ipynb` by double-clicking on it in the left side panel. Follow the instructions inside.

**Note: This step takes time. Expect to keep your computer on for at least 30 minutes while the downloads take place.**

**Note: You only need to complete this step one time. Once you have the two *model...* folders inside your *internal* folder, the models are downloaded and can be used by steps 3 and 4 as many times as needed to generate content.**

---

# Step 3. Generate profiles with profile pictures

Open `3_generate_actors.ipynb`.

Specify the number of profiles you would like to generate in the variable `num_profiles`. For example, `num_profiles = 100`. If you would like to change the image size, you may do so with the variable `image_size`.

The bios are filled with random occupations (from https://github.com/johnlsheridan/occupations/blob/master/occupations.csv but saved locally in the `internal/` folder). Everything else is generated using the Random User API.

## Run the program

Run the program by selecting *Kernel > Restart Kernel and Run All Cells...* in the menu bar at the top left of the screen. Results will be in `output > csv_files > actors.csv` and `output > profile_pictures`. You will see the words, "Profiles generated!!" at the bottom of the notebook when the code is finished running.

---

# Step 4. Generate posts

**Note: This must be done only after models are downloaded (step 2) and profiles are generated (step 3).**

Open `4_generate_posts.ipynb`.

## Get a Pexels API Key

**For Professor DiFranzo - I left mine in the notebook for convenience, so you can skip this step.**

You will need a Pexels API key for this notebook. Go to https://www.pexels.com/api/, and select "Get Started." Create an account. Once you do, you will receive an API Key. Please copy this and paste it into the API_KEY variable in the notebook. 

## Setting variables

Follow the instructions in the `4_generate_posts.ipynb` notebook for this section. 

## Run the program

Run the program by selecting *Kernel > Restart Kernel and Run All Cells...* in the menu bar at the top left of the screen. Results will be in `output > csv_files > posts.csv` and `output > profile_pictures`. You will see the words, "Posts generated!!" at the bottom of the notebook when the code is finished running.

---

# Conclusion

Finally, add the `output` folder contents to the Truman simulation. Copy the `csv_files` contents into Truman's `input` folder, and copy the images of the `profile_pictures` and `post_pictures` folders into the folders of the same name in the Truman project. 
