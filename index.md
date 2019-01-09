## Welcome to my GitHub/R-Studio Journal 

This journal is there to help me remember how I got there in the end (minus the dead ends).

### Get started with github

I started with the [hello world tutorial](https://guides.github.com/activities/hello-world/) to understand what this is all about.

### Get the desktop app for github

Next I installed the [github desktop app](https://desktop.github.com) to be able to sync a folder on my computer, which is much easier than editing online.

### Create a website

Next, I created a website using the [hugo academic template](https://themes.gohugo.io//theme/academic/post/getting-started/). 

### Create a book

Next, I created a guidebook for my module, following [this tutorial](http://seankross.com/2016/11/17/How-to-Start-a-Bookdown-Book.html) and these steps:

1. Fork the [bookdown-start repo](https://github.com/seankross/bookdown-start)
2. Rename the repository
3. Clone the repository to your desktop
4. Fetch origin in GitHub Desktop
5. Open R Studio and create a new project, select the cloned directory of the GitHub repository
6. Open _output.yml; change the book title and the split_by: section 

> *Note:* the split_by option is best for a short document so the whole text can be saved in the index.Rmd file.

7. Open _bookdown.yml and change the book_filename, and the repo:
8. Open index.Rmd and make the required changes.

### Create a papaja preprint

1. Install [papaja](https://crsh.github.io/papaja_man) in R Studio: 

`devtools::install_github("crsh/papaja")`

2. Follow the [readme instructions](https://github.com/crsh/papaja/blob/master/README.md)
3. Check the [apa6 LaTeX package](http://ctan.sharelatex.com/tex-archive/macros/latex/contrib/apa6/apa6.pdf) for options.

### Link up my github website with R Studio

1. Create a new R project
2. Select the folder that is already a git repo and has your site in it
3. Upload the .gitignore file (so git ignores the files that R Studio creates)

Voilà! Now I can edit, commit, push all from inside R Studio.

I also managed to link up my personal website which is built by hugo following [these instructions](https://itsalocke.com/blog/using-blogdown-with-an-existing-hugo-site/).

easy-peasy-lemon-squeezy... (almost!)


