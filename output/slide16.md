
**List Applications**
    
```
curl -k -X GET -u $MARATHON_USER:$MARATHON_PASSWORD \
	-H "Content-type: application/json" \
	$MARATHON_URL/apps \
	| python -m json.tool
	
# this will dump out a ton of data for every application that is deployed
# Let's filter it down to just the one we built 
	
curl -k -X GET -u $MARATHON_USER:$MARATHON_PASSWORD \
	-H "Content-type: application/json" \
	$MARATHON_URL/apps/$MYUSERNAME/data \
	| python -m json.tool
	
```
	

