## connection 

mysql -u root -p


## query to file 

mysql -u root -p -D database -e "select field from table group by field INTO OUTFILE '/tmp/query1.csv';"

