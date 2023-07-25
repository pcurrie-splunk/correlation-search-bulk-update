# correlation-search-bulk-update
Bulk update correlation searches

Requirement: Update multiple correlation searches together

Example 1: 
1. Create 5 test searches "TEST1-search1", "TEST2-search2", etc.
2. Create a lookup "SearchToMITRELookup" with a row for each search, and MITRE ATT&CK technique multi-value field for each
3. Create a script that gets the TEST* searches (validate this), then add the MITRE ATT&CK technique from the lookup as an annotation


From the doc here: https://dev.splunk.com/enterprise/docs/devtools/python/sdk-python/howtousesplunkpython/howtowork/

1. Create 5 test searches

# Create a saved search--search everything, return 1st 10 events
# Note: Do not include the 'search' keyword for a saved search
myquery = "index=_internal | head 10"
mysearchname = "TEST1"

mysavedsearch = service.saved_searches.create(mysearchname, myquery)
print "Created: " + mysavedsearch.name



1. Create saved search using REST: https://dev.splunk.com/enterprise/tutorials/module_getstarted/addsearches/
```
curl -k -u admin:splunk3du https://10.202.35.243:8089/services/saved/searches -d name="Top Replacement Costs" --data-urlencode description="Example search using REST" --data-urlencode search="index=devtutorial | top limit=20 REPLACEMENT_COST"
```
2. Turn this into a correlation search in ES by adding `action.correlationsearch.enabled      = 1`
```
curl -k -u admin:splunk3du https://10.202.35.243:8089/services/saved/searches -d name="Top Replacement Costs" --data-urlencode description="Example search using REST" --data-urlencode search="index=devtutorial | top limit=20 REPLACEMENT_COST"
```
3. 
4. 
