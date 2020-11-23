# Archaeology Data Services
Here are some photos of the graphs I tried to make using the code you provided:


After completing the preset activities I went to Archaeology Data Service to find a data set that I found interesting. 

New Spreadsheet Code: 
Eware <- read.csv(curl("http://ads.ahds.ac.uk/catalogue/adsdata/arch-788-1/dissemination/csv/imports_database/Eware.csv"), header = TRUE, row.names = "ID" )

View(Eware)

Use <- Eware %>%
  filter(str_detect(Use, "no sooting"))

#Use version
siteCounts <- table(Use$site)
siteCounts <- sort(siteCounts, decreasing=TRUE)
barplot(siteCounts, main="sites", xlab="site", las=2, cex.names=.5 )

#this was the mst common location for the vessals  
DinasPowys <- Use %>%
  filter(str_detect(site, "DINAS POWYS"))

View(DinasPowys)

DinasPowysCounts <- table(DinasPowys$Form)
DinasPowysCounts <- sort(DinasPowysCounts, decreasing=TRUE)
barplot(DinasPowysCounts, main="Uses", xlab="Use", las=2, cex.names=.5)

