
    **Consul DNS Lookup**
    
    ```
    # this shows an example command and output for reference.  
    	
    # do a regular lookup
    dig @control.mantl.domain.intra app-dev.service.consul
    	
    ; <<>> DiG 9.8.3-P1 <<>> @control.mantl.domain.intra app-dev.service.consul
    ; (3 servers found)
    ;; global options: +cmd
    ;; Got answer:
    ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 42128
    ;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0
    	
    ;; QUESTION SECTION:
    ;app-dev.service.consul.		IN	A
    	
    ;; ANSWER SECTION:
    app-dev.service.consul.	0	IN	A	10.101.129.119
    	
    ;; Query time: 187 msec
    ;; SERVER: 10.101.129.123#53(10.101.129.123)
    ;; WHEN: Tue Aug  2 16:13:21 2016
    ;; MSG SIZE  rcvd: 78	
    	
    # We get an A record back so we know the IP 
    # of the host running the app, but not the port
    	
    # Same lookup, but this time for the SRV record
    dig @control.mantl.domain.intra app-dev.service.consul SRV
    	
    ; <<>> DiG 9.8.3-P1 <<>> @control.mantl.domain.intra app-dev.service.consul SRV
    ; (3 servers found)
    ;; global options: +cmd
    ;; Got answer:
    ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 59685
    ;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
    	
    ;; QUESTION SECTION:
    ;app-dev.service.consul.		IN	SRV
    	
    ;; ANSWER SECTION:
    app-dev.service.consul.	0	IN	SRV	1 1 25797 green2-worker-001.node.green.consul.
    	
    ;; ADDITIONAL SECTION:
    green2-worker-001.node.green.consul. 0 IN A	10.101.129.119
    	
    ;; Query time: 140 msec
    ;; SERVER: 10.101.129.123#53(10.101.129.123)
    ;; WHEN: Tue Aug  2 16:13:23 2016
    ;; MSG SIZE  rcvd: 168
    	
    	
    # Now we have the IP and the Port so can access this service	
    ```

