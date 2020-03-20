## connection 

mysql -u root -p


## query to file 

mysql -u root -p -D database -e "select field from table group by field INTO OUTFILE '/tmp/query1.csv';"

## Log long queries

slow_query_log = 1
log-queries-not-using-indexes
long_query_time=1
log-slow-queries=/var/log/mysql/log-slow-queries.log 
