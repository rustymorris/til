## Splunk Notes

A splunk search job will remain active for 10 minutes after its run, afterwards splunk will need to run it again.

A shared search job will remain active for 7 days.

A splunk search will use the timezone of the user who run the search to display times.

wildcards:
fail*
failed NOT password
failed OR password

order of operation

1. NOT
2. OR
3. AND

Put exact phases in quotes. Use backslash to escape quotes in search.
info="user \"chrisV4\" not in database"


**SPL**

To output only certain fields, pipe to table with field names or pipe to fields
examples:

```
index=web sourcetype=access* status=200 product_name=*
| table JSESSIONId, product_name, price
```

```
index=web sourcetype=access* status=200 product_name=*
| fields JSESSIONId, product_name, price
```

```
Remove fields from display my using the minus sign
index=web sourcetype=access* status=200 product_name=*
| fields -JSESSIONId
```

Renaming fields
```
index=web sourcetype=access* status=200 product_name=*
| fields JSESSIONId, product_name, price
| rename JSESSIONID as "User Session"
```
