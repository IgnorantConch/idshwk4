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
  + if the count of 404 response > 2
  + and if the 404 ratio > 20% (404 ratid = 404 response/all response)
  + and if (the unique count of url response 404 / if the count of 404 response) > 0.5
  + then output" x.x.x.x is s scanner with y scan attemps on z urls" where
    + x.x.x.x is tje orig_h
    + y is the count of 404 response
    + z is the unique count of url response 404 
## You Need
+ Sumstats is option but not a requirement
+ you may use set,table and record to do the calculating
+ you may measure the time interval every time http_reply is triggered
## Reference
http_replt (https://docs.zeek.org/en/master/scripts/base/bif/plugins/Zeek_HTTP.events.bif.zeek.html#id-http_reply)
