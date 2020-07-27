This project is created for Sauce Labs using the open source tool created by Google, located in the 'tools' folder inside.
Navigate to tools/README.md to learn more about this tool, how to use it, and get resources

This document will be for documenting sauce_school specific changes and specifications.

#Initial setup
1. Install Go and nodeJS on your computer, as per [instructions here](https://medium.com/@zarinlo/publish-technical-tutorials-in-google-codelab-format-b07ef76972cd)

2. Download the [claat binary](https://medium.com/@zarinlo/publish-technical-tutorials-in-google-codelab-format-b07ef76972cd). When you insitalled GO on your computer, you should have a folder called go/bin and inside that file will be claat.

3. in your ~/.bash_profile add in
'
```
##Codelabs Path required
export PATH=$PATH:$HOME/go/bin
```

4. The project setup is labeled sauce_school_codelab. Within it you should see the folders tools/site. Inside of /site, you have a separate 'codelab' for each course (this is because each course will have it's own 'codelabs' landing page with several modules? subject to change)

5. To run a local copy, make sure that you have a markdown file. **!IMPORTANT at the top of the .md file , you need to have project information with the id- this is what your file generated for the codelab will be named. set it to the same name as your project directory (see below)of your codelab** (see below). Each codelab means a new landing page- each codelab is a course, with several lessons in it. Some examples name of 'codelab' directories include 'site/SeleniumJS' and site/Selenium Java'. Now run the command `claat export <filename.md>` to export it to a new directory with a .json file and index.html.

```summary: Module 1 Introduction to Selenium with JavaScript
id: Module1-SeleniumJS
categories: First draft
tags: Beginner
status: work in progress
authors: Lindsay Walker
Feedback Link: https://walkerweb.me
```

6. To serve it up locally, run `gulp serve --codelabs-dir=<codelab directory name>` e.g. `gulp serve --codelabs-dir=SeleniumJS`

7. When you create a new codelab markdown file, you can use the [Docs to Markdown tool](https://gsuite.google.com/marketplace/app/docs_to_markdown/700168918607), however there will be some HTML tags at the top you need to delete, as well as title cleanup you need to do
 - Make sure each title has one hash `#` for the course name. Each sub-category ('lesson') should have two hashes in front `##`)
 - Delete any HTML tags, they will screw things up
 - Make sure you delete any random `<p>` tags within the doc.
 - before each lesson with `##`, above it insert `<!-- ------------------------ -->` to denote a new pages
 - Images can mess things up. Make sure you list an image as  imagefolder/imagename.png. The image folder will be at the same level as the markdown page (not within a codelabs folder')
