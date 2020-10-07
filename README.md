# SECscraping
My name is Marco Bronzetti. I developed this short code for returning various useful links from the SEC EDGAR database. I found myself working on a project that required me to download numerous form and I figured out this can be helpful for other people too.

Up to now the script can return the link to the 10K, 10Q and 8K SEC webpage giving as input the CIK number and the year.

sec10k_url(cik_number, date) requires as argument the CIK and the year (1994,...) return the link on the SEC website

sec10q_url(cik_number, date, quarter) requires as argument the CIK, year (1994,...), quarter (1,2,3,4) return the link on the SEC website

sec8k_url(cik_number, date) requires as argument the CIK and the year (1994,...) return the link on the SEC website

sec_exhibit(link) takes as input one of the previous function and return a list that contains all the links to the Exhibits available on the SEC website

download_exhibit(sec_exhibit(), file_name) takes as input sec_exhibit and download the exhibits in txt version and ask you the name of the new file

download_exhibits10(sec_exhibit, file_name) exactly as above but returns only exhibits 10.**

file_parser(file_name, name): takes as input the file from which to parse and the name of the file in which the new infos will be stored, in this case i filter the text for specific words, due to the nature of the reasearch I am carrying out, you can easily change those strings.

mongo_this(sec_exhibit, id_post) upload all the exhibits in a mongodb, it ask the id of the post and store the whole file as a value in a dictionary

The two scripts download_file and mongo_file are used to iterate the previous functions over large dataset (IT CAN TAKE LONG TIME, BUT IT IS CONSISTENT WITH SEC robots.txt) they work properly as long as you upload as df1 an excel file that contains at least 4 columns with such headers: 'companyname_compustat'; 'cik'; 'year';'quarter'.

The use is really simple, just try:

print(sec10k_url(201493, 1994))

print(sec10q_url(201493, 1994, 2))

print(sec8k_url(201493, 1994))

print(sec_exhibit(sec10k_url(201493, 1994)))

print(sec_exhibit(sec10q_url(201493, 1994, 2)))

print(sec_exhibit(sec8k_url(201493, 1994)))

For any issue you can contact me at: bronzetti97@gmail.com or marco.bronzetti@studbocconi.it
