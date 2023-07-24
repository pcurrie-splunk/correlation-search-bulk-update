# correlation-search-bulk-update
Bulk update correlation searches

Requirement: Update multiple correlation searches together

Example 1: 

1. Create saved search using REST: https://dev.splunk.com/enterprise/tutorials/module_getstarted/addsearches/
```
curl -k -u admin:splunk3du https://10.202.35.243:8089/services/saved/searches -d name="Top Replacement Costs" --data-urlencode description="Example search using REST" --data-urlencode search="index=devtutorial | top limit=20 REPLACEMENT_COST"
```
2. 
3. 
