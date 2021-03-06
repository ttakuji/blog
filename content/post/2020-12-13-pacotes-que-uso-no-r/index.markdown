---
title: Pacotes que uso no R
author: ''
date: '2020-12-13'
slug: []
categories: []
tags:
  - R
  - packages
draft: yes
---


Comecei os cursos básicos de Tidyverse no coursera. Como são cursos introdutórios
gosto de anotar as dicas que vão aparecendo no meio do caminho. 


Nesse primeiro post vou separar os pacotes que são recomendados de se instalar no
computador.

## Pacote here



Utilizado para facilitar os caminhos em diferentes ambientes e computadores.
Ótimo para utilizar em projetos com a finalidade de não haver problemas de localização de arquivos.


## Pacote ProjectTemplate

Cria um diretório para projetos em R. Ótimo para ter um padrão nos projetos.
No curso que estou fazendo, estamos usando o template minimal, conforme mostro no código a seguir.


```r
library(ProjectTemplate)
create.project(project.name = "data_analysis",
               template = "minimal")
```
## Pacote readxl

Pacote para ler arquivos em xls, mais conhecido como excel. 

```r
library(readxl)
df_excel <- read_excel("filename.xlsx")

```

## Pacote googlesheets

Como deve se imaginar pelo nome, o pacote permite que faça download de planilhas online
do serviço da google. Ótimo para automatizar atualizações.


```r
#install.packages("googlesheets")
library(googlesheets)

#comando a seguir para fazer o login, abrirá uma tela
gs_auth(new_user = TRUE)

#uma vez feita autenticação, será possível ver quais planilhas possue através:
command gs_ls()
```


## Pacote readr

Leitura de arquivos em CSV, Comma-separated values.



```r
## install.packages("readr")
library(readr)

## read CSV into R
df_csv <- read_csv("sample_data - Sheet1.csv")

## look at the object
head(df_csv)

#save files in csv
write_csv(df_csv, path = "my_csv_file.csv")

```

## Pacote jsonlite

Para leitura de arquivos JSON. Muito comum na internet, princripalmente em API. 


```r
library(jsonlite)

# read JSON file into R
read_json("json_file.json")

# read JSON file into R and 
# simplifies nested lists into vectors and data frames
read_json("json_file.json", simplifyVector = TRUE)

```


## Pacote para banco de dados


```r
# install.packages("dbplyr")
library(dbplyr)
library(dplyr)

#Ler o banco de dados
db <- dbConnect(sqlite, "company.db")
dbListTables(db)

#carregar os dados de uma tabela
albums <- tbl(db, "albums")
artists <- tbl(db, "artists")

## This code is an example only
con <- DBI::dbConnect(RMySQL::MySQL(), 
  host = "database.host.com",
  user = "janeeverydaydoe",
  password = rstudioapi::askForPassword("database_password")
)

```





