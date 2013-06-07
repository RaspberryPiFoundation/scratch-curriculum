# Contributing New Translations

## Step 1 - Fork the repository

Click the `Fork` button in the top-right.

![Fork button](http://codeclub-assets.s3.amazonaws.com/public/contributing/fork.png)

## Step 2 - Clone to the repository to your computer

    cd ~/Documents
    git clone git@github.com:YOUR_NAME/scratch-curriculum.git
    cd scratch-curriculum

NB: Replace `YOUR_NAME` with your GitHub handle and `Documents` with
whatever folder on your machine you’d like keep your work in.

## Step 3 - Create a folder for your translation

Copy the 'English' folder and rename it appropriately e.g. 'Español'.

    cp -r English Español

## Step 4 - Translate!

You can translate anything and everything you like within your translation
folder. This means folder names, file names, and the contents of the Markdown,
PDF and Scratch files.

## Step 5 - Push your work

When you’re happy with your translation, run the following commands to
commit and push your work:

    cd ~/Documents/scratch-curriculum
    git add --all
    git commit -m 'Your message here, e.g. Add Spanish translation'
    git push

## Step 6 - Make a pull request

Click the `Pull Request` button.

![Pull request](http://codeclub-assets.s3.amazonaws.com/public/contributing/pull-request.png)

Give your pull request an appropriate message.

![Pull request message](http://codeclub-assets.s3.amazonaws.com/public/contributing/pull-request-editor.png)

## Step 7 - Ask another native speaker to review your pull request

Give another native speaker a link to your pull request, which will be
something like http://github.com/codeclub/scratch-curriculum/pulls/3

If they’re happy, they should leave a comment on the pull request with a
:+1: or similar message.

## Step 8 - We merge the translation!

At this point we’ll merge your pull request, your translation will become
part of the repository, available for everyone to use and benefit from,
and we’ll say thank you and give you a massive hug.

We’ll also give you commit access to this and the other repos, so from this
point in you’ll be able to make changes directly without needing to submit
a pull request.
