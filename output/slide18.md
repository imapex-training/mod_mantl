
**Delete Application**
    
```
curl -k -X DELETE -u $MARATHON_USER:$MARATHON_PASSWORD \
		-H "Content-type: application/json" \
		$MARATHON_URL/apps/$MYUSERNAME/data 
```


