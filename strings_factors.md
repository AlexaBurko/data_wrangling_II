strings and factors
================
Alexa Burko
2026-10-20

## strings and regex

``` r
string_vec = c("my", "name", "is", "alexa")

str_detect(string_vec, "alexa")
```

    ## [1] FALSE FALSE FALSE  TRUE

``` r
str_detect(string_vec, "my")
```

    ## [1]  TRUE FALSE FALSE FALSE

``` r
str_detect(string_vec, "My")
```

    ## [1] FALSE FALSE FALSE FALSE

``` r
str_replace(string_vec, "my", "My")
```

    ## [1] "My"    "name"  "is"    "alexa"

``` r
# replace "my" in the string with "My"
```

``` r
string_vec = c(
  "i think we all rule for participating",
  "i think i have been caught",
  "i think this will be quite fun actually",
  "it will be fun, i think"
  )

str_detect(string_vec, "i think")
```

    ## [1] TRUE TRUE TRUE TRUE

``` r
#"i think" anywhere in string 

str_detect(string_vec, "^i think")
```

    ## [1]  TRUE  TRUE  TRUE FALSE

``` r
# "i think" at the beginning

str_detect(string_vec, "^i think$")
```

    ## [1] FALSE FALSE FALSE FALSE

``` r
# "i think" at the end
```

``` r
string_vec = c(
  "Time for a Pumpkin Spice Latte!",
  "went to the #pumpkinpatch last weekend",
  "Pumpkin Pie is obviously the best pie",
  "SMASHING PUMPKINS -- LIVE IN CONCERT!!"
  )

str_detect(string_vec, "[Pp]umpkin")
```

    ## [1]  TRUE  TRUE  TRUE FALSE

``` r
# brackets mean that that letter can either be capital or lowercase
```

``` r
string_vec = c(
  '7th inning stretch',
  '1st half soon to begin. Texas won the toss.',
  'she is 5 feet 4 inches tall',
  '3AM - cant sleep :('
  )

str_detect(string_vec, "^[0-9][a-zA-Z]")
```

    ## [1]  TRUE  TRUE FALSE  TRUE

``` r
# brackets define ranges
# detects any number 0-9 followed immediately by any letter capital or lowercase
```

``` r
string_vec = c(
  'Its 7:11 in the evening',
  'want to go to 7-11?',
  'my flight is AA711',
  'NetBios: scanning ip 203.167.114.66'
  )

str_detect(string_vec, "7.11")
```

    ## [1]  TRUE  TRUE FALSE  TRUE

``` r
# detects the numbers 7 and 11 with any character (.) in between 
```

``` r
string_vec = c(
  'The CI is [2, 5]',
  ':-]',
  ':-[',
  'I found the answer on pages [6-7]'
  )

str_detect(string_vec, "\\[")
```

    ## [1]  TRUE FALSE  TRUE  TRUE

``` r
# the slash slash tells it to look for the subsequent character 
```

## quick note on factors

``` r
vec_sex = factor(c("male", "male", "female", "female"))

as.numeric(vec_sex)
```

    ## [1] 2 2 1 1

``` r
vec_sex = fct_relevel(vec_sex, "male")
```

Import NSDUH

``` r
url = "https://www.samhsa.gov/data/sites/default/files/NSDUHsaeShortTermCHG2015/NSDUHsaeShortTermCHG2015.htm"

drug_use_html = read_html(url)
```
