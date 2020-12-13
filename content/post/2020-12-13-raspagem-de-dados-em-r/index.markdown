---
title: Raspagem de dados em R
author: ''
date: '2020-12-13'
slug: []
categories: []
tags:
  - R
  - web scraping
draft: yes
---

Em R usamos muito o pacote rvest que vem de Harvest, do inglês, colheita. 
Para facilitar a coleta, podemos utilizar uma ferramenta no google chrome
chamada [SelectorGadget](https://chrome.google.com/webstore/detail/selectorgadget/mhjhnkcfbdhnjickkkdbjoemdmbfginb)

No navegador utilizamos o SelectorGadget para gerar o XPath ![](images/teste.png)

E o código para raspagem é: 


```r
## load package
# install.packages("rvest")
library(rvest) # this loads the xml2 package too!
## Loading required package: xml2
## 
## Attaching package: 'rvest'
## The following object is masked from 'package:purrr':
## 
##     pluck
## The following object is masked from 'package:readr':
## 
##     guess_encoding
## provide URL
packages <- read_html("http://jhudatascience.org/stable_website/webscrape.html") # the function is from xml2

## Get Packages
packages %>% 
  html_nodes("strong") %>%
  html_text() 
 ## [1] "rvest"        "httr"         "dbplyr"       "jsonlite"     "googlesheets"
```

