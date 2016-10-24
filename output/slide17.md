
    **Update Application**	
    
    ```
    curl -k -X PUT -u $MARATHON_USER:$MARATHON_PASSWORD \
    	-H "Content-type: application/json" \
    	$MARATHON_URL/apps/$MYUSERNAME/data \
    	-d '{"instances": 3}' \
    	| python -m json.tool
    	
    ```


