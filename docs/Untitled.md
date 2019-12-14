
---
title: "Web Exercises"
output: webex::webex_default
---



This is a Web Exercise template created by the [psychology teaching team at the University of Glasgow](http://www.psy.gla.ac.uk), based on ideas from [Software Carpentry](https://software-carpentry.org/lessons/). This template shows how instructors can easily create interactive web documents that students can use in self-guided learning.

The webex package provides a number of functions that you use in [inline R code](https://github.com/rstudio/cheatsheets/raw/master/rmarkdown-2.0.pdf) to create HTML widgets (text boxes, pull down menus, buttons that reveal hidden content). Examples are given below. Knit this file to HTML to see how it works.

**NOTE: To use the widgets in the compiled HTML file, you need to have a JavaScript-enabled browser. The widgets don't work in the built-in RStudio browser. In the built-in browser, click the "Open in Browser" button to open the file in your operating system's browser.**

## Fill-In-The-Blanks (`fitb()`)

Create fill-in-the-blank questions using `fitb()`, providing the answer as the first argument.

- 2 + 2 is <input class='solveme nospaces' size='1' data-answer='["4"]'/>

You can also create these questions dynamically, using variables from your R session.



- The square root of 16 is: <input class='solveme nospaces' size='1' data-answer='["4"]'/>

The blanks are case-sensitive; if you don't care about case, use the argument `ignore_case = TRUE`.

- What is the letter after D? <input class='solveme nospaces ignorecase' size='1' data-answer='["E"]'/>

If you want to ignore differences in whitespace use, use the argument `ignore_ws = TRUE` (which is the default) and include spaces in your answer anywhere they could be acceptable.

- How do you load the tidyverse package? <input class='solveme nospaces ignorecase regex' size='20' data-answer='["library( tidyverse )","library( \"tidyverse\" )","library( &apos;tidyverse&apos; )"]'/>

You can set more than one possible correct answer by setting the answers as a vector.

- Type a vowel: <input class='solveme nospaces ignorecase' size='1' data-answer='["A","E","I","O","U"]'/>

## Multiple Choice (`mcq()`)

- "Never gonna give you up, never gonna: <select class='solveme' data-answer='["let you down"]'> <option></option> <option>let you go</option> <option>turn you down</option> <option>run away</option> <option>let you down</option></select>"
- "I <select class='solveme' data-answer='["bless the rains"]'> <option></option> <option>bless the rains</option> <option>guess it rains</option> <option>sense the rain</option></select> down in Africa" -Toto

## True or False (`torf()`)

- True or False? You can permute values in a vector using `sample()`. <select class='solveme' data-answer='["TRUE"]'> <option></option> <option>TRUE</option> <option>FALSE</option></select>

## Hidden solutions and hints

You can fence off a solution area that will be hidden behind a button using `hide()` before the solution and `unhide()` after, each as inline R code.  Pass the text you want to appear on the button to the `hide()` function.

If the solution is an RMarkdown code chunk, instead of using `hide()` and `unhide()`, simply set the `webex.hide` chunk option to TRUE, or set it to the string you wish to display on the button.

### Example problem

**Recreate the scatterplot below, using the built-in `cars` dataset.**

\begin{figure}

{\centering \includegraphics[width=1\linewidth]{Untitled_files/figure-latex/unnamed-chunk-3-1} 

}

\caption{**CAPTION THIS FIGURE!!**}(\#fig:unnamed-chunk-3)
\end{figure}


<div class='solution'><button>I need a hint</button>

See the documentation for `plot()` (`?plot`)

</div>


<!-- note: you could also just set webex.hide to TRUE -->


```r
plot(cars$speed, cars$dist)
```

<!-- TO CHANGE WIDGET COLOURS:
  move command below out of this HTML comment area
  and then re-compile;
  unfilled becomes yellow, correct becomes pink 
     

<style>
    .solveme { border-color: #FFFF00; }
    .solveme.correct { border-color: #FF3399; }
</style>


-->
