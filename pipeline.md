# Walkthrough for creating a classification pipeline


## Introduction

The aim of this walkthrough is to create a classification pipeline in Cloud Run.
The end goal is to have a service which could accept input from a web form and output
a classification, together with auxiliary features such as metrics and logging.
The idea is to simulate what we might go through to create a risk estimation service
for Trevor which could be plugged into web applications.

Throughout this walkthrough, I am using GCP while signed in from my google.com account.
This has some implications for things like the folder hierarchy, and I expect some changes
might need to be made for accounts at Trevor. We should copy and modify this walkthrough
appropriately.

We'll do most of the work in Cloud Shell. It's a shell which runs in the browser, onto a VM
with 5GB of storage. To activate Cloud Shell, click this button

<walkthrough-open-cloud-shell-button/>

You can also activate the shell from the <walkthrough-cloud-shell-icon/> icon.

### Steps of the walkthrough

1. Setting up the project.
1. Creating and deploying a service.
1. Accepting input.
1. Calling out to a classifier.
1. Calling the service from other code.


## Setting up the project

1. <walkthrough-project-billing-setup/>
1. Authorize the Cloud Shell to access your project.
    ```bash
    gcloud auth logging
    ```

   If you are already authorized, you don't need to do this again.

1. Set an environment variable to the ID of the project you created or selected in step 1, for the convenience of later commands.
    ```bash
    PROJECT_ID=   # Fill in your project ID here.
    ```

1. Set this as the current project.
    ```bash
    gcloud config set project $PROJECT_ID
    ```

... API set up ...
