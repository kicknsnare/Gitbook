# 🔰 Splunk Filters

```bash
#Filter the fields
| fields <field1> + <field2> + <field3>
#Search for raw text
| search "Word"
#Remove Duplicates
| dedup <fieldname>
#Rename the field name
| rename  <fieldname>
#Table Time
| table _time
#Reverse the content
| reverse
#Create a Table with different fields
| table <field_name1> <fieldname_2>  
#Return the first 10 Events or specific number of event
| head 
| head <number>  
#Return the last 10 Events or specific number of event
| tail
| tail <number>
#Order the fields in ascending or descending order
| sort <field_name>  
#Return Frequent values for the top 10 events
| top  <field_name>
| top limit=6 <field_name>
#Return the least frequent values or bottom 10 results
| rare <field_name>
| rare limit=6 <field_name>
#Show the results in raw events mode with fields highlighted
| highlight  <field_name1> <field_name2>
##################### Stats ##########################
stats avg(field_name)
stats max(field_name)	
stats min(field_name)
stats sum(field_name)
stats count(function) AS new_NAME
stats count(fieldname)
#################### CHARTS #######################
#transform the data into tables or visualizations
| chart <function>
EXAMPLE:
| chart count by User
#time series chart
| timechart function  <field_name>
EXAMPLE:
| timechart count by Image

```

