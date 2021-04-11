# idshwk4
# Detect http scan based on 404 response
## There are some scenarios will generate the 404 response:
+ the attacker has no  knowledge of the target site before scanning
+ site configuration error,user mistype
+ the spiders repeat crawling the pages not existed
+ downloading tools repeat download the faling url
## The Algorithm Requirement
+ make 404 statistics on orig_h
+ In every 10 minutes
++ if the count of 404 response > 2
