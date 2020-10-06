# SECscraping
My name is Marco Bronzetti. I developed this short code for returning various useful links from the SEC EDGAR database. I found myself working on a project that required me to download numerous form and I figured out this can be helpful for other people too.

Up to now the script can return the link to the 10K, 10Q and 8K SEC webpage giving as input the CIK number and the year.

sec10k_url(cik_number, date) requires as argument the CIK and the year (1994,...) return the link on the SEC website
sec10q_url(cik_number, date, quarter) requires as argument the CIK, year (1994,...), quarter (1,2,3,4) return the link on the SEC website
sec8k_url(cik_number, date) requires as argument the CIK and the year (1994,...) return the link on the SEC website

sec_exhibit(link) takes as input one of the previous function and return a list that contains all the links to the Exhibits available on the SEC website

The use is really simple, just try:

print(sec10k_url(201493, 1994))

print(sec10q_url(201493, 1994, 2))

print(sec8k_url(201493, 1994))

print(sec_exhibit(sec10k_url(201493, 1994)))

print(sec_exhibit(sec10q_url(201493, 1994, 2)))

print(sec_exhibit(sec8k_url(201493, 1994)))

For any issue you can contact me at: bronzetti97@gmail.com or marco.bronzetti@studbocconi.it
