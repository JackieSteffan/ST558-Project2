ST 558 Project 2
================
Hannah Park
10/15/2020

## Code for Automation

``` r
dayofweek <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday")
output_file <- paste0(dayofweek, "Analysis", ".md")
params <- lapply(dayofweek, FUN = function(x){list(dayofweek = x)})
reports <- tibble(output_file, params)

apply(reports, MARGIN = 1, 
      FUN = function(x){render(input = "AnalysisCode.Rmd",
                               output_file = x[[1]],
                               params = x[[2]])})
```

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##           cp
    ## 1 0.07039248
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model
    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output MondayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS MondayAnalysis.md --to html4 --from gfm --output MondayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c124562a9.html

    ## 
    ## Output created: MondayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##          cp
    ## 1 0.1214922
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output TuesdayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS TuesdayAnalysis.md --to html4 --from gfm --output TuesdayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c4b184944.html

    ## 
    ## Output created: TuesdayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##         cp
    ## 1 0.167221
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output WednesdayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS WednesdayAnalysis.md --to html4 --from gfm --output WednesdayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c7c933890.html

    ## 
    ## Output created: WednesdayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##          cp
    ## 1 0.1309504
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model
    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output ThursdayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS ThursdayAnalysis.md --to html4 --from gfm --output ThursdayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c1fd9b7b.html

    ## 
    ## Output created: ThursdayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##          cp
    ## 1 0.1707028
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output FridayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS FridayAnalysis.md --to html4 --from gfm --output FridayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c7dc33cfb.html

    ## 
    ## Output created: FridayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##          cp
    ## 1 0.1168913
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output SaturdayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS SaturdayAnalysis.md --to html4 --from gfm --output SaturdayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c418e61ac.html

    ## 
    ## Output created: SaturdayAnalysis.md

    ## 
    ## 
    ## processing file: AnalysisCode.Rmd

    ##   |                                                                              |                                                                      |   0%  |                                                                              |..                                                                    |   3%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....                                                                  |   5%
    ## label: setup (with options) 
    ## List of 1
    ##  $ include: logi FALSE
    ## 
    ##   |                                                                              |......                                                                |   8%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |........                                                              |  11%
    ## label: data (with options) 
    ## List of 2
    ##  $ message: logi FALSE
    ##  $ warning: logi FALSE

    ## Parsed with column specification:
    ## cols(
    ##   instant = col_double(),
    ##   dteday = col_date(format = ""),
    ##   season = col_double(),
    ##   yr = col_double(),
    ##   mnth = col_double(),
    ##   holiday = col_double(),
    ##   weekday = col_double(),
    ##   workingday = col_double(),
    ##   weathersit = col_double(),
    ##   temp = col_double(),
    ##   atemp = col_double(),
    ##   hum = col_double(),
    ##   windspeed = col_double(),
    ##   casual = col_double(),
    ##   registered = col_double(),
    ##   cnt = col_double()
    ## )

    ##   |                                                                              |.........                                                             |  14%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...........                                                           |  16%
    ## label: full-data-correlation-plot (with options) 
    ## List of 1
    ##  $ fig.cap: chr "Correlation Plot"

    ##   |                                                                              |.............                                                         |  19%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...............                                                       |  22%
    ## label: full-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |.................                                                     |  24%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |...................                                                   |  27%
    ## label: full-data-histograms

    ##   |                                                                              |.....................                                                 |  30%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.......................                                               |  32%
    ## label: full-data-scatterplot

    ##   |                                                                              |.........................                                             |  35%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................                                            |  38%
    ## label: day-data-contingency-table

    ## The following object is masked _by_ .GlobalEnv:
    ## 
    ##     dayofweek

    ##   |                                                                              |............................                                          |  41%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..............................                                        |  43%
    ## label: day-data-summary-statistics-table
    ##   |                                                                              |................................                                      |  46%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |..................................                                    |  49%
    ## label: day-data-boxplot

    ##   |                                                                              |....................................                                  |  51%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |......................................                                |  54%
    ## label: dat-data-scatterplot

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

    ##   |                                                                              |........................................                              |  57%
    ##    inline R code fragments
    ## 
    ##   |                                                                              |..........................................                            |  59%
    ## label: regression-tree-final-model
    ##   |                                                                              |............................................                          |  62%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................                         |  65%
    ## label: regression-tree-final-model-results

    ##   |                                                                              |...............................................                       |  68%
    ##    inline R code fragments
    ## 
    ##           cp
    ## 1 0.06165483
    ##   |                                                                              |.................................................                     |  70%
    ## label: regression-tree-final-model-predictions
    ##   |                                                                              |...................................................                   |  73%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.....................................................                 |  76%
    ## label: boosted-tree-final-model

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ## Warning in (function (x, y, offset = NULL, misc = NULL, distribution =
    ## "bernoulli", : variable 3: holiday has no variation.

    ##   |                                                                              |.......................................................               |  78%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.........................................................             |  81%
    ## label: boosted-tree-final-model-results

    ##   |                                                                              |...........................................................           |  84%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |.............................................................         |  86%
    ## label: boosted-tree-final-model-parameters-table
    ##   |                                                                              |..............................................................        |  89%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |................................................................      |  92%
    ## label: boosted-tree-final-model-predictions
    ##   |                                                                              |..................................................................    |  95%
    ##   ordinary text without R code
    ## 
    ##   |                                                                              |....................................................................  |  97%
    ## label: model-comparison
    ##   |                                                                              |......................................................................| 100%
    ##   ordinary text without R code

    ## output file: AnalysisCode.knit.md

    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS AnalysisCode.utf8.md --to gfm --from markdown+autolink_bare_uris+tex_math_single_backslash --output SundayAnalysis.md --standalone --table-of-contents --toc-depth 2 --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\default.md" 
    ## "C:/Program Files/RStudio/bin/pandoc/pandoc" +RTS -K512m -RTS SundayAnalysis.md --to html4 --from gfm --output SundayAnalysis.html --standalone --self-contained --highlight-style pygments --template "C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\preview.html" --variable "github-markdown-css:C:\Users\hyeon\Documents\R\win-library\4.0\rmarkdown\rmarkdown\templates\github_document\resources\github.css" --email-obfuscation none --metadata pagetitle=PREVIEW

    ## 
    ## Preview created: C:\Users\hyeon\AppData\Local\Temp\RtmpicTliO\preview-5a2c46bf29ac.html

    ## 
    ## Output created: SundayAnalysis.md

    ## [1] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/MondayAnalysis.md"   
    ## [2] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/TuesdayAnalysis.md"  
    ## [3] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/WednesdayAnalysis.md"
    ## [4] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/ThursdayAnalysis.md" 
    ## [5] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/FridayAnalysis.md"   
    ## [6] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/SaturdayAnalysis.md" 
    ## [7] "C:/Users/hyeon/Desktop/558/Project 2/ST558-Project2/SundayAnalysis.md"
