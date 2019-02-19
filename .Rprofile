# Installation des packages si nécessaire et chargement
CRANLibrary <- function(Packages) {
  InstallAndLoad <- function(Package) {
    if (!Package %in% utils::installed.packages()[, 1]) {install.packages(Package, repos="https://cran.rstudio.com/")}
    require(Package, character.only = TRUE)
  }
  invisible(sapply(Packages, InstallAndLoad))
}
# Packages sur GitHub
GitHubLibrary <- function(Packages) {
  InstallAndLoad <- function(Package) {
    Package_split <- str_split(Package, "/", simplify = TRUE)
    if (!Package_split[1, 2] %in% utils::installed.packages()[, 1]) {remotes::install_github(Package)}
    require(Package_split[1, 2], character.only = TRUE)
  }
  invisible(sapply(Packages, InstallAndLoad))
}
# Ajouter les packages nécessaires ici
library("stats") # Avant tidyverse
CRANLibrary(c("alphahull", "entropart", "kableExtra", "rgdal", "tidyverse"))
GitHubLibrary("EricMarcon/SpatDiv")
