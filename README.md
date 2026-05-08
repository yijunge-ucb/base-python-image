# base-python-image

This is the repo for DataHub Python base image and intended for DataHub admin use only.

## Steps

### Step 1: 
- Admins make changes in apt.txt to manage system packages and environment.yaml to manage Conda and Pip packages.
- Once the PR is merged, the Github action for building the base image is triggered. 

### Step 2:
- In the Github logs, look for the new base image tag. Alternatively, you can navigate to the artifact registry on Google cloud console and find the tag for the latest image. 
- Nagivate to a hub with the fancy profile configured (e.g. nature.datahub.berkeley.edu), and lauch a server with the newly built base image.
- Test the basic functionalities, including:
  1. Write a file in the terminal
  2. Open a notebook, write a notebook, run a notebook, and save a notebook.
- Test the recent changes, including:
  1. Versions (by running pip show \<package\>)
  2. New functionalities tied to a specific version
   
### Step 3:
Once the base image is tested and everything looks good, manaully dispatch the "Trigger Downstream Builds" workflow in Github actions. 

1. Which downstream group to build?
   
   Choose "base" if you want to build the downstream R base image.
   Choose "user" if you want to build the downstream hub specific user images. 
2. Base image name (e.g. ucb-datahub-2018/testing/base-python-image)
   
   Use the base image name you have obtained in step 2.
3. Base image SHA/tag to propagate
   
   Use the base image tag you have obtained in step 2.


