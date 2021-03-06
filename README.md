# viewDat


Use this keyboard shortcut to view a data.frame or data.table in RStudio's built-in data viewer.
	
The shortcut wraps all the text on your current line in `View()` and executes it, which will result in RStudio opening a data viewer tab with your data.
	
The shortcut will work as long as the complete line returns a data.frame/data.table/tibble when executed normally. It will not work if there is a comment at the end of the line, or for piped functions that wrap multiple lines.
	
To use, you must bind the function to a keyboard shortcut in RStudio by going to `Tools -> Modify Keyboard Shortcuts...` and finding the entry "View data on cursor line". I have bound it to `Ctrl + ,`.

The shortcut will work when executed both from a .R file open in the editor or from the RStudio console. Because it wraps the whole line, the shortcut will work on the following lines:

`iris`

`data.table(iris)[, mean(Sepal.Length), by=.(Species)][Species == 'setosa']`

`iris %>% filter(Species == "setosa")`

I find this particularly useful with data.table queries, as they are almost always on one line.

# Installation

Install with `devtools`: `devtools::install_github("t-morrison/viewDat")`