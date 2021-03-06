# Welcome to my GitHub/R-Studio Journal 

This journal is there to help me remember how I got there in the end (minus the dead ends).

## Get started with github

I started with the [hello world tutorial](https://guides.github.com/activities/hello-world/) to understand what this is all about.

1. Download and install Git.
2. Download and install RStudio (1.1.383 or higher).
3. Open RStudio.
4. Create the remote repository on GitHub
5. On GitHub.com, create a new repository.
6. Click Add .ignore and select R.
7. Click Create repository.
8. Clone the repository with RStudio
  - On the right side of the screen, click Clone or download.
  - Click the Copy to clipboard icon to the right of the repository URL.
9. Open RStudio on your local environment.
10. Click File, New Project, Version Control, Git.
11. Paste the repository URL and enter TAB to move to the Project directory name field.
12. Click Create Project.

# Get started with jsPsych

I've created a [new page](./jsPsych.html) for this.

## Install the Academic Theme with R Studio

Click [here](https://sourcethemes.com/academic/docs/install/#install-with-rstudio) for the instructions.

## Get the desktop app for github

Next I installed the [github desktop app](https://desktop.github.com) to be able to sync a folder on my computer, which is much easier than editing online.

## Create a website

Next, I created a website using the [hugo academic template](https://themes.gohugo.io//theme/academic/post/getting-started/). 

## Create a book

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

An alternative route to simply create a book offline and export it as a .pdf or an ebook is to:

1. Download the GitHub repository https://github.com/rstudio/bookdown-demo as a Zip file, then unzip it locally.
2. Open the bookdown-demo repository you downloaded in RStudio by clicking bookdown-demo.Rproj.
3. Open the R Markdown file index.Rmd and click the button Build Book on the Build tab of RStudio.

> *Note:* For more details, look at https://bookdown.org/yihui/bookdown/get-started.html

### Add a cover page before the title page in pdf file generated by bookdown

The trick is to turn off LaTeX's \maketitle command, create the cover page, then turn \maketitle back on and execute it if you want the title page as well.

Starting with the standard bookdown demo, append the following two lines to the end of preamble.tex

\let\oldmaketitle\maketitle
\AtBeginDocument{\let\maketitle\relax}
This saves the \maketitle command as \oldmaketitle and then turns off the original \maketitle. In the same directory, now create a before_body.tex file that contains the following lines

\thispagestyle{empty}
\begin{center}
{\Huge A BOOK}
\includegraphics{cover.png}
{\huge by Me}
\end{center}

\let\maketitle\oldmaketitle
\maketitle
This inserts a page at the beginning of your output pdf, then returns \maketitle to its original state and then executes it. If you already have a before_body.tex file, just add the lines to the end. In the above example, I've included some text before and after the image, just to show that one can.

Finally you need to place your cover image file (cover.png) in the same directory. and build your pdf_book. This will produce a cover page with a title ("A BOOK") followed by the cover picture and then the author ("by Me").

In this example I've used a png file, but pdf or jpg files also work fine. If you have a more complicated directory structure, as in the standard bookdown example, you may have to modify the path to the necessary files, e.g. "latex/preamble.tex" instead of "preamble.tex".

Source: https://stackoverflow.com/a/48371022/6919113

### Customise LaTeX output in bookdown

> There are a large number of other YAML options that you can specify for LaTeX output, such as the paper size, font size, page margin, line spacing, font families, and so on. See http://pandoc.org/MANUAL.html#variables-for-latex for a full list of options.

Source: https://bookdown.org/yihui/bookdown/latexpdf.html

### Automatically update the date

```date: "`r Sys.Date()`"```


## Create a papaja preprint

1. Install [papaja](https://crsh.github.io/papaja_man) in R Studio: 

`devtools::install_github("crsh/papaja")`

2. Follow the [readme instructions](https://github.com/crsh/papaja/blob/master/README.md)
3. Check the [apa6 LaTeX package](http://ctan.sharelatex.com/tex-archive/macros/latex/contrib/apa6/apa6.pdf) for options.

## Link up my github website with R Studio

1. Create a new R project
2. Select the folder that is already a git repo and has your site in it
3. Upload the .gitignore file (so git ignores the files that R Studio creates)

Voilà! Now I can edit, commit, push all from inside R Studio.

I also managed to link up my [personal website](https://profgaelle.com) which is built by hugo following [these instructions](https://itsalocke.com/blog/using-blogdown-with-an-existing-hugo-site/).

easy-peasy-lemon-squeezy... (almost!)


