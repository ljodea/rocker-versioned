FROM rocker/rstudio:3.4.1

RUN apt-get update -qq && apt-get -y --no-install-recommends install \
  libxml2-dev \
  libcairo2-dev \
  libsqlite-dev \
  libmariadbd-dev \
  libmariadb-client-lgpl-dev \
  libpq-dev \
  libssh2-1-dev \
  libsecret-1-dev \
  unixodbc-dev \
  odbc-postgresql \
  && R -e "source('https://bioconductor.org/biocLite.R')" \
  && install2.r --error \
    --deps TRUE \
    tidyverse \
    dplyr \
    devtools \
    formatR \
    remotes \
    xgboost \
    Iso \
    Matrix \
    redshiftTools \
    odbc \
    config \
    stringr \
    lubridate \
    stringdist

## Notes: Above install2.r uses --deps TRUE to get Suggests dependencies as well,
## dplyr is already part of tidyverse, but listed explicitly to get suggested dependencies.
## In addition to the the title 'tidyverse' packages, devtools is included for package development.
## RStudio wants formatR for rmarkdown, even though it's not suggested.
## remotes included for installation from heterogenous sources including git/svn, local, url, and specific cran versions
